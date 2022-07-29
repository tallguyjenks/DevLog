

### Changing the names of the default import

so if you have a User [[JavaScript Classes|class]] you're importing but in the new file you import that into you want to import that class but call it something different, then what you can do is basically treat it like a base class (which it is) and say:

`import U from '/user.js'`

because the User class is the default export its assuming we're saying something like this if we were in python

```python
import pandas as pd
```

except that its `import User as U`
