# Basic-Calculator

Programming language: `Python`

- `README.md`: For the documentation
- `requirements.py`: The project dependencies.
  - `pytest`: This framework makes it easy to write small, readable tests, and can scale to support complex functional testing for applications and libraries.
- `app.py`: The source code our calculator app
- `test.py`: Contains the tests cases 

### Next Steps 

Clone the project locally, implement the features and commit to GitHub, observe the CI results


#### The `add` method

#### Implementation

In `app.py`

```py
class Calculator:
    def __init__(self):
        pass

    def add(self, num1, num2):
        return num1 + num2
```

In `test.py`

```py
import pytest
from app import Calculator

# Fixture to create an instance of the Calculator class
@pytest.fixture
def calculator():
    return Calculator()

# Test case for the add method
def test_add(calculator):
    assert calculator.add(2, 3) == 5
    assert calculator.add(-1, 1) == 0
    assert calculator.add(0, 0) == 0
    assert calculator.add(-5, -7) == -12
```

#### Commit and Push

```sh
git add app.py test.py
git commit -m 'Done with the add function'
git push
```

### The `div` method

#### Implementation

In `app.py`

Add the method `div` to the class `Calculator`

We will intentionally simulate a bug by omitting the error handling for division by zero. 

```py
def div(self, num1, num2):
  return num1 / num2
```

In `test.py`

```py
# Test case for the div method
def test_div(calculator):
    assert calculator.div(4, 2) == 2
    assert calculator.div(-1, 1) == -1
    assert calculator.div(0, 5) == 0

# Test case for division by zero
def test_div_by_zero(calculator):
    with pytest.raises(ValueError):
        calculator.div(10, 0)
```

#### Commit and Push

```sh
git add app.py test.py
git commit -m 'Done with the div function'
git push
```