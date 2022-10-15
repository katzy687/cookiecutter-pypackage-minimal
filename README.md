# cookiecutter-pypackage-minimal

My forked, opinionated take on a minimal [cookiecutter](https://github.com/audreyr/cookiecutter) template for Python
packages.

### Usage

```commandline
  pip install cookiecutter
  cookiecutter https://github.com/katzy687/cookiecutter-pypackage-minimal.git
```

See cookicutter.json for all parameters that are passed into the template.

### Python Versions

Defaults to python 3.9. Can provide a custom override and will be forwarded to multiple files in template.
The full list of PyPI classifiers can be found [here](https://pypi.org/classifiers/).

### Testing

* **Uses [pytest](https://docs.pytest.org) as the default test runner**
* **Use [Tox](https://tox.readthedocs.io) to manage test environments**
* **Define testing dependencies in `tox.ini`**
* **`tests` directory should not be a package**

### Precommit and Linting

Use [pre-commit](https://pre-commit.com/) as the lint and formatter runner, both locally and in Github Actions CI.
See `.pre-commit-config.yaml` file for default linter settings and to modify to exclude files etc.

**Uses the following formatters / linters, listed in `requirements-dev.txt`:

- [Black](https://github.com/psf/black)
- [Flake8](https://flake8.pycqa.org/en/latest/)
- [Pylint](https://pypi.org/project/pylint/)

## Github Actions

- Some default workflows for linting and release packaging are included.
- Pushes to all branches triggers linting workflow.
- Pushing tags that start with "v" will kick off release workflow.
- To upload package to Pypi, must add Repository secrets `PYPI_API_TOKEN` and `TEST_PYPI_TOKEN`
- [Release Changelog Builder](https://github.com/marketplace/actions/release-changelog-builder) for adding PR details to
  releases. Add more labels to `changelog_config.json`
- Add some [Git Emojis](https://gitmoji.dev/) to commits and CI jobs ⚡️

### Versioning And Release

Use [Bump2version](https://pypi.org/project/bump2version/) to bump `version.txt` and create matching "v" release tag.
Pushing this tag will kick off CI flow for release
See `.bumpversion.cfg` for additional settings

### LICENSE

* **MIT license by default**
  This template provides you the classic [MIT](https://choosealicense.com/licenses/mit/) licence: it lets people do
  almost anything they want with your project, including to make and distribute closed source versions.
  If you [choose another license](https://choosealicense.com/), you also need to update `setup.py`