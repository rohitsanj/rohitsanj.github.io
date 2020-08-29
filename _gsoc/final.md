---
title: GSoC Blog 7 - Work Product Submission
layout: post
permalink: /gsoc/final-report
---
## Introduction

This is my work product submission for the Google Summer of Code 2020 project on testbook. I had an amazing time working with my mentor Matthew Seal. I would like to thank him for guiding me in every step of the way.

Testbook is a unit testing framework for testing code in Jupyter Notebooks. With testbook, you can now write pytest style unit tests for notebooks, in separate .py files. Testbook can now help you write maintainable and reliable Jupyter Notebooks.

## What work was done

[Testbook][testbook] was built from scratch with the help of existing libraries such as [nbclient][nbclient] and [nbformat][nbformat]. We have done 6 [releases][releases] of `testbook` so far and at the time of writing this report, we are currently at version `0.2.2`.

All deliverables in the proposal have been fulfilled.

### Links to work done

- [Pull Requests raised](https://github.com/nteract/testbook/pulls?q=is%3Apr+label%3AGSoC-2020)
- [Commits](https://github.com/nteract/testbook/commits?author=rohitsanj)
- [Issues raised](https://github.com/nteract/testbook/issues?q=is%3Aissue+label%3AGSoC-2020+)

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

## What's next

Here is what is in store for future releases of testbook

- [Provide support for kernels other than ipython](https://github.com/nteract/testbook/issues/58)
- [Code coverage for notebooks](https://github.com/nteract/testbook/issues/12)

## Conclusion and Acknowledgement

I would like to thank the team at **National Solar Observatory, Colorado, USA**  for considering use of testbook. I would also like to thank the team at **Mindtree, Bangalore, India** for providing critical feedback.

I really hope that more and more organizations embrace unit testing for Jupyter Notebooks. We have already seen a few open source projects investigating the use of testbook and we would love to see more of that.

I'm extremely glad that I got this opportunity to create and design a new open source project. I would like to thank nteract, NumFOCUS and Google for this opportunity.

[testbook]: https://github.com/nteract/testbook
[releases]: https://pypi.org/project/testbook/#history
[nbclient]: https://github.com/jupyter/nbclient
[nbformat]: https://github.com/jupyter/nbformat
