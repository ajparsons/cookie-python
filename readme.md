# Poetry cookiecutter template

Cookiecutter template for seting up a new poetry-based python package. You can use locally (if the python cookiecutter package is installed using):

```
python -m cookiecutter https://github.com/ajparsons/cookie-python/
```

## Templating in GitHub

Based on the general approach of https://github.com/simonw/python-lib, this repo also has [a Github template](https://github.com/ajparsons/poetry-auto-template/) that can be used to set up a new template in github. 

## Features
 
The default package uses:

* [poetry](https://python-poetry.org/) for package management,
* [pytest](https://docs.pytest.org/en/7.1.x/) for testing,
* [black](https://black.readthedocs.io/en/stable/) for linting,
* [pyright](https://github.com/microsoft/pyright) for typechecking. 

New repositories include config files and Dockerfile for developing in VS Code or Codespaces, so the development process can happen end to end in Github. (Or not! Will still worked cloned locally). 

The test suite contains meta tests for alignment between the `__version__` of the package and the poetry version, and that the current version is documented in the change log. 

The template version includes a default GitHub Action for testing on Python 3.8-3.10, and publishing to pypi.

By default, the test action requires pytest, black and pyright to return no errors.

The default licence is the MIT Licence. Change if needed. 

# Publishing the package

* Set a GitHub Actions secret for PYPI_TOKEN. 
* For the initial publish. In the Actions tab for a repo, trigger a manual workfork flow with the 'force to pypi' box ticked.
* Subsequently, if the poetry version is bumped and all tests pass - the GitHub Action will automatically publish on push to the main branch.
