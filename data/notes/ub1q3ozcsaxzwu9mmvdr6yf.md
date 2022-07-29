

- Try out [[s.l.python]] [profiling][8]

```python
import cProfile
import pstats
with cProfile.Profile() as pr:
    yourfunctionhere()
stats = pstats.Stats(pr)
stats.sort_stats(pstats.SortKey.TIME)
stats.print_stats()
```

[8]: https://docs.python.org/3/library/profile.html
