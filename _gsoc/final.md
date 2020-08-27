---
title: GSoC Blog 7 - Work Product Submission
layout: post
permalink: /gsoc/final-report
---

This is my work product submission for the Google Summer of Code 2020 project on testbook. I have had an amazing time working with my amazing mentor Matthew Seal. I would like to thank him for guiding me in every step of the way.

## What work was done?

[Testbook][testbook] was built from scratch with the help of existing libraries such as [nbclient][nbclient] and [nbformat][nbformat]. We have done 6 [releases][releases] of `testbook` so far and at the time of writing this report, we are currently at version `0.2.2`.

All deliverables in the proposal have been fulfilled.

### Links to work done

- [Commits](https://github.com/nteract/testbook/commits?author=rohitsanj)
- [Pull Requests raised](https://github.com/nteract/testbook/pulls?q=is%3Apr+author%3Arohitsanj+)
- [Issues raised](https://github.com/nteract/testbook/issues?q=is%3Aissue+author%3Arohitsanj)

### Features Added

- Execute all or some specific cells before unit test
- Share kernel context across multiple tests (using pytest fixtures)
- Support for patching objects
- Inject code into Jupyter notebooks

### Technical Talks

#### SciPy 2020 Lightning Talks

I delivered a lightning talk at SciPy 2020 where I talked about testbook. The video can be found [here](https://youtu.be/oz1hA4c-i0E?t=72) and the slides that were presented can be found [here](https://speakerdeck.com/rohitsanj/testbook-unit-test-your-jupyter-notebooks).

#### PyCon India 2020

Matthew and I have jointly submitted a talk proposal about testbook to PyCon India 2020. We are yet to hear from the PyCon India team about talk acceptances, we are anxiously waiting!

The talk proposal can be found [here](https://in.pycon.org/cfp/2020/proposals/unit-testing-jupyter-notebooks-testbook~epYwV/).

## What's next?

- Provide support for kernels other than ipython
- Code coverage for notebooks

## Conclusion

I'm glad to have brought testbook to a fairly usable state. I really hope that more and more organizations embrace unit testing for Jupyter Notebooks. We have already seen a few open source projects investigating the use of testbook and we would love to see more of that.

[testbook]: https://github.com/nteract/testbook
[releases]: https://pypi.org/project/testbook/#history
[nbclient]: https://github.com/jupyter/nbclient
[nbformat]: https://github.com/jupyter/nbformat
