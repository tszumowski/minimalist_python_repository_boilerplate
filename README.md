# New Repository Configuration

This directory contains boilerplate files for new python repositories.

**Reference Medium Articles:**
* [Using Jenkins to Automate Packaging and Deployment](https://medium.com/@tszumowski/using-jenkins-to-automate-packaging-and-deployment-cb8aba34a61a)
* [The Anatomy of a Minimalist Python Repository Boilerplate](https://medium.com/@tszumowski/the-anatomy-of-a-minimalist-python-repository-boilerplate-26cb2a296ba4)

## .idea - PyCharm Black Formatter
**watcherTasks.xml**

This contains the default configuration for using the Black formatter on any `.py` file in PyCharm. Black needs to be installed in the Python Interpreter selected in PyCharm for it to work.

## pre-commit formatting and style-guide reinforcement
**.pre-commit-config.yaml**

This should be placed at the top level of the repository. It provides opt-in configuration files for developers to auto-format their code using black, and auto-check for PEP 8 conformance with flake8. It can save time so that CI/CD builds don't fail due to simple linting or formatting.

Install pre-commit by first `pip install pre-commit`. Then `pre-commit install`. 

**requirements.dev**
In the event you want to run black/flake8 manually, or ptest from the command-line, these install the packages and plugins needed.

## .python-version

This file also can be placed at the top level. It defines what python version should be used by default for all subdirectories, using pyenv. pyenv searches recursively upwards so you don't need it in the subdirectories. You can always override with a local .pyenv-version file.

## pytest.ini, .coveragerc

Default configuration for running `pytest`. This ini includes various plugins to provide code coverage, XML reporting (for tools like Jenkins), and parallel operation.

## .flake8

Provides defaults for flake8 code formatting. Includes ignore-lines that make it compatible with `black`

## Jenkinsfile Examples

These are example of how to automate linting, testing, and dispatching python packages and applications. See the headers of each file for details and usage.
They were modified from a project-specific version so they weren't tested. YMMV. Leave a message in the Issues if you have questions on usage or issues
using them.

**Jenkinsfile.package**
* For linting, testing, packaging, and uploading wheels of a python package

**Jenkinsfile.application**
* For linting, testing, building a Docker image, and pushing Docker image of a deployable Python3 application container. 

