# README

<!-- Remember to change the URL from pytemplate to the name of your project -->
![Tests](https://github.com/HWRacing/pytemplate/actions/workflows/tests.yml/badge.svg)

A template for python packages. All further documentation assumes that your current working directory is this repository (i.e. the directory where this README is).

## Using This Template

To start using this template, rename the `src/projectname` directory, replacing `projectname` with the name of your package (making sure it doesn't already exist on pypi). Next, edit `setup.cfg` to replace all references to `pytemplate` to the name of your package (and if necessary, change all of the HWRacing stuff to your own details). Also, edit the test status link at the top of this README. Then, you can start writing code and tests. Every time you push a commit, your tests will run, and before you merge, more extensive tests will be run with tox.

## Installing Your Package for Testing

When you clone your package repo to your local machine, run `pip install -e .`. This command installs the package in such a way that if you edit the source code, the package on your machine is updated too.

## Running Tests

To run some quick unit tests, just run `pytest`. If you want more in-depth tests across multiple virtual environments (by default several versions of python), then run `tox`. If you want to check your type hinting, run `mypy .` (this should happen in tox, but it doesn't for some reason).

## Setting Up Automated Deployment

To allow for automated deployment, [you need to upload your package to pypi once manually](https://packaging.python.org/en/latest/tutorials/packaging-projects/). Once that is done, set a GitHub secret named `PYPI_API_TOKEN` to the package's API key.

## Releasing Versions

When you want to release a version, change the `version = ` line in `setup.cfg` to your desired version, then create a new release on GitHub with a matching version number. The GitHub action will automatically upload this version to pypi.
