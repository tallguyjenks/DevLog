---
title: pytest
tags: library
---

- **References:**
	- https://testdriven.io/blog/testing-python/
	- [Calm Code pytest](https://calmcode.io/pytest/introduction.html)
		-
		- `blackjack.py`
		  collapsed:: true
			-
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
		- `test_blackjack.py`
		  collapsed:: true
			-
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
			- A more robust way to stay [[DRY]] is to use: ((60be8411-7d36-4c4f-8f0f-56c733eb3294)) from [[pytest]]
				-
				  ```python
				  @pytest.mark.parametrize("cards,score", [('JK', 20), ('KKK', 0), ('AA', 12), ('AK', 21)])
				  def test_simple_usecase(cards, score):
				      assert card_score(cards) == score
				  ```
		- Run tests with `pytest --verbose` or configure auto process to do that
			- pytest is looking for files and functions whose names begin with `test_*`
			- You can run singular unit tests with the following syntax:
				-
				  ```
				  pytest --verbose test_blackjack.py::test_Simple_case4
				  ```
		- [[pytest]] in a package
		  collapsed:: true
			-
			  ```
			  ├── blackjack
			  │   ├── __init__.py
			  │   └── common.py
			  ├── setup.py
			  └── tests
			      ├── __init__.py
			      └── test_blackjack.py
			  ```
				- **blackjack**
					- `__init__.py` should be empty
					- `common.py` (user preference on naming, example said "common utilities")
						-
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
				- **tests**
					- `__init__.py` should be empty
					- `test_blackjack.py`
						-
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
			- [[HTML]] output: `pytest --cov blackjack --cov-report html`
			-
-