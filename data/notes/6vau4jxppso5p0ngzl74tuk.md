

- `Author:` alfredo-deza
- `Link:` <https://paiml.com/docs/home/books/testing-in-python/chapter02-testing-conventions/>
- `Reviewed Date:` [[import.research.article.2021.11.12]]

---

- author links to have his tests in the source code directory alongside existing codebase and mirror the directory structure of the code.
- a separate sub-directory under the `tests/` directory for tests like sending an API call are a functional test and not something as granular to test in a unit like a sum function
- have tests even if living at the top level of the project (this is so the test code doesnt ship with the source code and is just less code to move around) and have them mirror the directory structure of the code base so if the `src/` directory has `src/utilities/utils.py` then there should be `tests/utilities/test_utils.py`

## Special test class methods

Aside from test naming conventions, there are other special names that you should be aware of when using classes. These names should be considered reserved, and should only be used for their intended purpose. These are all the special methods:

`setup`: This method allows to provide attributes or anything else that is used by tests. By convention, it is called once before every test method in the class is executed. If lots of tests are using some sample data, it can be defined once here instead of having it referenced over and over in every single test method.

`teardown`: This method allows to perform any cleanup actions needed by tests. Just like the setup method, it gets called once, but after every test method in the class is executed. For example, if a test is always leaving behind artifacts like files that shouldn’t be present, this special method could remove them, so that the next test doesn’t have a polluted environment.

`setupclass`: Similar to setup, but instead of running before every test is executed it runs once before starting a test in a class.

`teardownclass`: This method runs once after all tests in the class have been executed.

If you are wondering why `__init__` is not mentioned in this list, it is because you should not have one for test classes. Historically, `unittest.TestCase` (Python’s standard library for testing) didn’t have them, and it relied on setup and teardown class methods, and tools like pytest skips collection of test classes if it detects an `__init__` method in them.

