
## Code Block

2 colons after a paragraph and indent next section then that becomes a code Block

```rst
this is an ordinary paragraph::

    def say_hi():
        print('Hello world')

And back to regular text
```

Using double colons default renders code as python so you can be more explicit with

```rst
this is an ordinary paragraph

.. code-block: python

    def say_hi():
        print('Hello world')

And back to regular text
```

the `.. code-block: python` is something called a directive
