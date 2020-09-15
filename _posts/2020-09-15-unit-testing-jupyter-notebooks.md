---
title: Unit Testing Jupyter Notebooks
layout: post
---

TLDR: We built a library called [testbook](https://github.com/nteract/testbook) for unit testing notebooks.

---

Jupyter Notebooks have been around for quite some time now and are being used extensively in the data science domain - mainly for experimentation and visualization. However, in the recent times, notebooks have been making headway into production environments. 

Some companies like Netflix have readily adopted notebooks in their production pipelines using tools like papermill and nteract. Read more about that [here][netflix-blog]. With this, it becomes extremely important to have reliable and maintainable notebooks.

Previous attempts at unit testing notebooks involved:

- **Writing tests in the notebook itself:** This approach makes the hard to read and maintain. 
- **Testing against saved notebook outputs:** This would not be useful in real world situations where data usually changes, or when there are non-deterministic outputs to be tested.
- **Writing integration tests for the whole notebook:**: There are tools like [papermill][papermill] which can be used for this. (Although the purpose of papermill is _slightly_ different)

**However, for unit tests there was no such library available. So.. [Matthew][Matthew] and I built one!**

## Testbook

Testbook is a unit testing framework for testing code in Jupyter Notebooks. Testbook will allow for unit tests to be run against notebooks in separate test files, hence treating .ipynb files as .py files.

Here is an example of a unit test written using testbook

Consider the following code cell in a Jupyter Notebook:

```python
def func(a, b):
   return a + b
```

You would write a unit test using testbook in a Python file as follows:

```python
import testbook


@testbook.testbook('/path/to/notebook.ipynb', execute=True)
def test_func(tb):
   func = tb.ref("func")

   assert func(1, 2) == 3
```

We designed the API in such a way that it looks and feels like a normal unit test, except it would be running in the notebook. Also, since testbook is only provides the assertion part of the _equation_ (pun intended), you can use testbook with practically any unit testing Python framework.

### Features

- Write conventional unit tests for Jupyter Notebooks
- Execute all or some specific cells before unit test
- Share kernel context across multiple tests (using pytest fixtures)
- Support for patching objects
- Inject code into Jupyter notebooks
- Works with any unit testing library - unittest, pytest or nose

## Use Cases

1. Education Industry

    Testbook can be used to write evaluation scripts for assignments submitted using Jupyter Notebooks. The team at [Jovian.ml](https://jovian.ml) is currently using testbook to conduct automated evaluation of assignments submitted for their course [Data Analysis with Python: Zero to Pandas](https://jovian.ml/learn/data-analysis-with-python-zero-to-pandas).

2. Testing ETL Workflows

    The team at [National Solar Observatory, Colorado](https://nso.edu) have investigated the use of testbook for testing their ETL workflows which are written using notebooks.


## Outreach

Testbook has been very well received by the community so far. 

<!-- <a href="https://twitter.com/MichelleUfford/status/1278126518716121089">
    <img alt="Michelle" src="/assets/tweets/michelle-tweet.webp" width="70%" style="margin-bottom: 10px; border: 1px solid black;">
</a> -->

<blockquote class="twitter-tweet" data-theme="light"><p lang="en" dir="ltr">So happy to see an OSS solution for unit testing <a href="https://twitter.com/ProjectJupyter?ref_src=twsrc%5Etfw">@ProjectJupyter</a> notebooks. This is a game-changer for notebook reliability, and it substantially increases the viability of notebooks for mission-critical production use. Nice work, <a href="https://twitter.com/imrohitsanj?ref_src=twsrc%5Etfw">@imrohitsanj</a>! 👏 <a href="https://t.co/o7rbC6N8w7">https://t.co/o7rbC6N8w7</a></p>&mdash; Michelle Ufford (@MichelleUfford) <a href="https://twitter.com/MichelleUfford/status/1278126518716121089?ref_src=twsrc%5Etfw">July 1, 2020</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-conversation="none" data-theme="light"><p lang="en" dir="ltr">Nice! So good to have tests in a separate file than the artifact (notebook) being tested.</p>&mdash; Amit Rathi (@amittrathi) <a href="https://twitter.com/amittrathi/status/1278202229825011712?ref_src=twsrc%5Etfw">July 1, 2020</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

We are desperately looking for more users to try out testbook.

If you are looking for assistance on setting up a unit testing suite for your notebooks, you can reach out to me directly at [sanjay.rohit2@gmail.com](mailto:sanjay.rohit2@gmail.com) and I would be more than willing to help you.

Thank you for reading my blog! Please let me know what you think in the comments below, I'd love to have a chat.

---

**Testbook links:**

- [GitHub](https://github.com/nteract/testbook/)
- [Docs](http://testbook.readthedocs.io/)
- [PyPI](https://pypi.org/project/testbook/)


[netflix-blog]: https://netflixtechblog.com/notebook-innovation-591ee3221233
[nbval]: https://nbval.readthedocs.io/en/latest/
[papermill]: https://papermill.readthedocs.io/
[Matthew]: https://github.com/mseal
