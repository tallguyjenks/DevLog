

```bash
python -m pip install mitoinstaller
python -m mitoinstaller install
```

```python
import mitosheet
import pandas as pd

df = pd.DataFrame.from_dict(
    {
        "col1": [1,2,3,4,5],
        "col2": [6,7,8,9,10],
    }
)

mitosheet.sheet(df)
```

![alt](assets/images/Pasted_image_20211129113658.png)

- Related:
  - [[pandas|import.software.language.python.library.pandas]]
  - [[polars|import.software.language.python.library.polars]]
