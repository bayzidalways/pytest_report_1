Python Testing Example: pytest
==============================
This example is part of the
[Python Testing 101 series](https://automationpanda.com/2017/03/06/python-testing-101-introduction/)
from [Automation Panda](https://automationpanda.com/).
It will work for Python 2 and 3.

Project Structure
-----------------
This project has two modules:
* `com.automationpanda.example.calc_func` contains math functions.
* `com.automationpanda.example.calc_class` contains a basic Calculator class.

Test modules are placed under the `tests` directory.
Note that `tests` is *not* a Python package and has no "__init__.py" file.

Requirements
------------
- Python 3.x
- `pytest`
- `pytest-cov` (for coverage reports)

Install dependencies (if not already installed):

```bash
python -m pip install pytest
```

```bash
python -m pip install pytest-cov
```

Running Tests
-------------
pytest has many command line options with a powerful discovery mechanism:

```bash
python -m pytest
```

```bash
python -m pytest -v
```

```bash
python -m pytest tests/test_calc_func.py
```

```bash
python -m pytest tests/test_calc_class.py
```

```bash
python -m pytest --junitxml=results.xml
```

```bash
python -m pytest -h
```

It is also possible to run pytest directly with the "pytest" or "py.test" command,
instead of using the longer "python -m pytest" module form. However, the shorter
command does *not* append the current directory path to *PYTHONPATH*.

Coverage Reports
----------------
Generate an HTML coverage report using `pytest-cov`. The output will be placed in the `htmlcov/` directory.

Run tests with coverage for the `com` package and generate HTML:

```bash
python -m pytest --cov=com --cov-report=html
```

Open the report at:
- `htmlcov/index.html`

Pytest Configuration
--------------------
You can make common options default by adding them to `pytest.ini`:

```ini
[pytest]
addopts = -v --cov=com --cov-report=html
testpaths = tests
```

GitHub: Commit htmlcov
----------------------
If you want the HTML coverage report committed to the repository (and visible on GitHub),
make sure `.gitignore` allows it. Add this line:
