

### Black Jack Repo Project Example

- [Sample Repo for this project](https://github.com/koaning/blackjack/)

#### blackjack.py

```python
def card_score(cards):
  numbers = [c for c in cards if c in "23456789"]
  faces = [c for c in cards if c in "JQK"]
  n_aces = sum([1 for c in cards if c == "A"])
  score = sum([int(i) for i in numbers]) + len(faces) * 10
  while n_aces > 0:
	  score += 1 if score + 11 > 21 else 11
	  n_aces -= 1
  return score if score <= 21 else 0
```

#### test_blackjack.py

```python
import pytest

from blackjack import card_score

def test_simple_usecase1():
  card_score("JK") == 20

def test_simple_usecase2():
  card_score("JKQ") == 0

def test_simple_usecase3():
  card_score("KA") == 21

def test_simple_usecase4():
  card_score("AA") == 12
```

- A more robust way to stay [[DRY|terms.dry]] is to use [[pytest|import.pytest]]

```python
@pytest.mark.parametrize("cards,score", [('JK', 20), ('KKK', 0), ('AA', 12), ('AK', 21)])
def test_simple_usecase(cards, score):
  assert card_score(cards) == score
```

- Run tests with `pytest --verbose` or configure auto process to do that
  - pytest is looking for files and functions whose names begin with `test_*`
  - You can run singular unit tests with the following syntax:

```bash
pytest --verbose test_blackjack.py::test_Simple_case4
```

#### Blackjack with DRY Pytests

- [[pytest|import.pytest]] in a package

```
├── blackjack
│   ├── __init__.py
│   └── common.py
├── setup.py
└── tests
  ├── __init__.py
  └── test_blackjack.py
```

##### blackjack

- `__init__.py` should be empty
- `common.py` (user preference on naming, example said "common utilities")

```python
def card_score(cards):
  if len(cards) < 2:
	  raise ValueError("The `card_score` function requires at least 2 cards.")
  if not isinstance(cards, str):
	  raise ValueError("The input for `card_score` needs to be a string.")
  numbers = [c for c in cards if c in "23456789"]
  faces = [c for c in cards if c in "JQK"]
  n_aces = sum([1 for c in cards if c == "A"])
  score = sum([int(i) for i in numbers]) + len(faces) * 10
  while n_aces > 0:
	  score += 1 if score + 11 > 21 else 11
	  n_aces -= 1
  return score if score <= 21 else 0
```

##### tests

- `__init__.py` should be empty
- `test_blackjack.py`

```python
import pytest

from blackjack.common import card_score

@pytest.mark.parametrize("cards,score", [('JK', 20), ('KKK', 0), ('AA', 12), ('AK', 21)])
def test_simple_usecase(cards, score):
  assert card_score(cards) == score
```

- To be able to work on the package in developer mode you'll need to run;
  - `python setup.py develop`
- And from here you can safely run pytest again.
- `pytest --verbose`
- `pytest-cov` for code coverage testing
  - `python -m pip install pytest-cov`
  - [[s.m.html]] output: `pytest --cov blackjack --cov-report html`
- [Calm Code Conftest](https://calmcode.io/test/conftest.html)
  - For greater code reusability and provide data to the testing suite, you can use `conftest.py` in the `tests` directory
  - This allows you to repeat yourself less and have a single location that feeds data into the testing suite instead of making the data for each test individually.

```python
from clumper import Clumper # our custom module
import pytest

@pytest.fixture(scope="module")
def base_clumper():
  data = [
	  {"data": [i for _ in range(2)], "i": i, "c": c}
	  for i, c in enumerate("abcdefghijklmnopqrstuvwxyz")
  ]
  return Clumper(data)

# So that tests like this:

def test_headtail_size():
  data = [{'i': i} for i in range(10)]
  c = Clumper(data)
  assert len(c.head(10)) == 10
  assert len(c.tail(10)) == 10
  assert len(c.head(5)) == 5
  assert len(c.tail(5)) == 5

# can become like:

def test_headtail_size(base_clumper):
  assert len(base_clumper.head(10)) == 10
  assert len(base_clumper.tail(10)) == 10
  assert len(base_clumper.head(5)) == 5
  assert len(base_clumper.tail(5)) == 5
```
