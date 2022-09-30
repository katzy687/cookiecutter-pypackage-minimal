cookiecutter-pypackage-minimal
==============================

My forked, opinionated take on a minimal [cookiecutter](https://github.com/audreyr/cookiecutter) template for Python packages

Usage
-----

    pip install cookiecutter
    git clone https://github.com/kragniz/cookiecutter-pypackage-minimal.git
    cookiecutter cookiecutter-pypackage-minimal/

You should then change the classifiers in `{{ package_name }}/setup.py` - it is assumed that the project will run on the latest versions of Python 2 and 3, so you should remove any classifiers that do not apply. The full list of PyPI classifiers can be found [here](https://pypi.org/classifiers/).


### LICENSE

* **MIT license by default**
  This template provides you the classic [MIT](https://choosealicense.com/licenses/mit/) licence: it lets people do almost anything they want with your project, including to make and distribute closed source versions.
  If you [choose another license](https://choosealicense.com/), you also need to update the `{{ package_name }}/setup.py` file:
  adjust the `classifiers` and `license` fields accordingly.

### Testing

* **Use [Tox](https://tox.readthedocs.io) to manage test environments**
  Tox provides isolation, runs tests across multiple Python versions, and ensures the package can be installed.
* **Uses [pytest](https://docs.pytest.org) as the default test runner**
  This can be changed easily, though pytest is a easier, more powerful test library and runner than the standard library's unittest.
* **Define testing dependencies in `tox.ini`**
  Avoid duplicating dependency definitions, and use `tox.ini` as the canonical description of how the unittests should be run.
* **`tests` directory should not be a package**
  The `tests` directory should not be a Python package unless you want to define some fixtures.
  But the best practices are to use [PyTest fixtures](https://docs.pytest.org/en/latest/fixture.html) which provides a better solution.
  Therefore, the `tests` directory has no `__init__.py` file.
