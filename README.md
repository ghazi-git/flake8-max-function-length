# flake8-max-function-length

A configurable [flake8](https://github.com/pycqa/flake8) plugin to enforce a maximum function/method length.

[![PyPI](https://img.shields.io/pypi/v/flake8-max-function-length)](https://pypi.org/project/flake8-max-function-length/)
[![PyPI - License](https://img.shields.io/pypi/l/flake8-max-function-length)](https://github.com/ghazi-git/flake8-max-function-length/blob/main/LICENSE)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)

## Installation

Install with `pip`

```shell
pip install flake8-max-function-length
```

## Configuration Options

The package has only one rule `MFL000` to check that function length is equal or lower to a maximum value.
By default, the function length should be lower than 50 lines and is calculated based on its content ignoring
its docstring, comments and empty lines. Still, you have the ability to customize that based on the following
options:

- `--max-function-length=n`: Maximum allowed function length. (Default: 50)
- `--mfl-include-function-definition`: Include the function definition line(s) when calculating the function length.
(Default: disabled)
- `--mfl-include-docstring`: Include the length of the docstring when calculating the function length.
(Default: disabled)
- `--mfl-include-empty-lines`: Include empty lines inside the function when calculating the function length.
(Default: disabled)
- `--mfl-include-comment-lines`: Include comment lines when calculating the function length. (Default: disabled)

## Usage with pre-commit

```yaml
repos:
  - repo: https://github.com/pycqa/flake8
    rev: '6.0.0'
    hooks:
      - id: flake8
        #args: [ --max-function-length, '100', --mfl-include-docstring, --mfl-include-comment-lines ]
        additional_dependencies: [ "flake8-max-function-length==0.7.0" ]
```

## Changelog

### [UNRELEASED]
#### Added

- Add badges to README.md and show it in PyPI

### [0.7.0] - 2023-02-18
#### Added

- Rule to enforce a limit on function/method length.
- Allow changing the maximum function length and how the function length is calculated via configuration options.


## Similar tools

- flake8-functions has a similar rule for maximum function length, however, it [doesn't exclude for empty lines
and comments](https://github.com/best-doctor/flake8-functions/issues/9).
- Pylint has the [too-many-statements](https://pylint.readthedocs.io/en/latest/user_guide/checkers/features.html#design-checker-messages)
rule, which is also similar to this one. Still, I find it easier to reason about number of lines as opposed to
number of statements.

## License

This project is [MIT licensed](LICENSE).
