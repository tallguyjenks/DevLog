

- `Author:` Felipe Florencio Garcia
- `Link:` <https://medium.com/dev-today/why-you-need-to-use-staticmethod-in-your-python-code-and-the-benefits-of-it-f777a5f21de6>
- `Publish Date:` 2021.11.28
- `Reviewed Date:` [[log.daily.2021.12.13]]

---

## Before

```python
class Calendar:
    
    def __init__(self, date):
        self.year = date.year
        self.month = date.month
        self.day = date.day
        self.weekday = date.weekday()
    
    
    def is_leap_year(self):
        return self.year % 400 == 0 or 
               (self.year % 4 == 0 and self.year % 100 != 0)
    
    
    def is_weekend(self):
        return self.weekday > 4
```

![alt](assets/images/Pasted_image_20211213151355.png)

We want to decouple the `is_weekend` and `is_leap_year` from the calendar class instance because they relate to any date not just that class instance.

## After

```python
class Calendar:
    
    def __init__(self, date):
        self.year = date.year
        self.month = date.month
        self.day = date.day
        self.weekday = date.weekday()
    
    
    @staticmethod
    def is_leap_year(date):
        return date.year % 400 == 0 or 
        (date.year % 4 == 0 and date.year % 100 != 0)
    
    
    @staticmethod
    def is_weekend(date):
        return date.weekday() > 4
```

Ok, the changes are:

1. Add the decorator `@staticmethod`;
2. Rename the expected parameter to be a date object;
3. Adjust the is_weekend function to get weekday as function and not variable.

Usage:

![alt](assets/images/Pasted_image_20211213151513.png)

## Benefits

> **The benefits of using it and when to use it.**
> The most important to take from this decorator is the purpose of using it.
> You should consider this decorator when writing any function that you believe is connected to the “subject” or the class that you are using but do not necessarily need that “subject” or class where you created the function.
> By doing this you can decouple the function itself, but still, keep it organized and with a clear meaning for which purpose can be used.
> From now on, any piece of code that you want to be reusable, but, at the same time you want to make it clear the “meaning” of when or how it could be used you should consider using this decorator.

