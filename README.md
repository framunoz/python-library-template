<!-- Pytest Coverage Comment:Begin -->
<!-- Pytest Coverage Comment:End -->

[![cov](doc/img/coverage-badge.svg)](doc/img/coverage-badge.svg)

# Python-Library-Template

This is a template for a Python library. It includes a README.md file, 
a .gitignore file, some Github Actions, a directory for the library code
and a directory for the tests. A module for logging is included in the 
library code.

## Using the template

This template is available as a repository on GitHub. To start a new 
library using this template, click on the green "Use this template"
button on the repository page (or blue if you are using dark mode).
Or simply click 
[here](https://github.com/new?template_name=python-library-template&template_owner=framunoz). 

## Adding a license

This template does not include a license file. If you want to add a
license to your project, you can do so by creating a new file called
`LICENSE` in the root directory of the project. You can use the
[choosealicense.com](https://choosealicense.com/) website to help you
choose a license.

GitHub allows you to add a license to your project if you create a file
called `LICENSE` in the root directory of the project. You can choose a
license from a list of common licenses or add a custom license.

## Starting a new library

Before starting a new library, you should change the name of the library
as you wish. You can do this by changing the name of the directory
`library`. 

Next, you should install ``poetry`` if you haven't already. You can do this
by running the following command:

```bash
pip install --upgrade pip
pip install poetry
```

Then, you should run the following command to initialize a new Python
project:

```bash
python -m poetry init
```
    
Poetry will ask you some questions about the project. You can answer them
as you wish. After that, you can see the `pyproject.toml` file that
Poetry has created. The tree structure of the project should look like this:

```
<PROJECT-NAME>
├── .github
│   └── workflows
│       └── pep8.yml
│       └── tests.yml
├── .gitignore
├── README.md
├── pyproject.toml
├── <LIBRARY-NAME>
│   └── __init__.py
│   └── logging_.py
└── tests
    └── __init__.py
```

Where `<LIBRARY-NAME>` is the name of the library you chose.

For further information on how to use Poetry, you can check this
[tutorial](doc/basic_poetry_usage.md).

## Coverage badge

You can add a coverage badge to your README.md file by adding the
following lines to the file:

```markdown
[![cov](doc/img/coverage-badge.svg)](doc/img/coverage-badge.svg)
```

For this, you need to install the `pytest`, `pytest-cov` and `genbadge`
packages. You can do this by running the following command:

```bash
poetry add --dev pytest pytest-cov genbadge
```

Then, you can run the following command to generate the coverage badge:

```bash
python -m pytest --durations=20 --doctest-modules -v --color=yes --cov=./ --cov-report=xml:reports/coverage/coverage.xml
python -m genbadge coverage -o doc/img/coverage-badge.svg
```
The coverage badge will be saved and updated automatically in the
`doc/img` directory.
