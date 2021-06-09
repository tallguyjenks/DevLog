---
title: pytest
tags: library
---

- **References:**
	- https://testdriven.io/blog/testing-python/
	- [Calm Code pytest](https://calmcode.io/pytest/introduction.html)
		- `blackjack.py`
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
			-
			  ```python
			  from blackjack import card_score
			  
			  def test_simple_usecase():
			      card_score("JK") == 20
			  ```
			- A more robust way to stay [[DRY]] is to use: ((60be8411-7d36-4c4f-8f0f-56c733eb3294)) from [[pytest]]
				-
				  ```python
				  
				  ```
		- Run tests with `pytest --verbose` or configure auto process to do that
			- pytest is looking for files and functions whose names begin with `test_*`
			- You can run singular unit tests with the following syntax:
				-
				  ```
				  pytest --verbose test_blackjack.py::test_Simple_case4
				  ```
-
-