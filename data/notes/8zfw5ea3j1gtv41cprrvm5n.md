

- [[s.l.python]] [Python is a Bad Programming Language][1]
- [[s.l.python]] [[terms.etl]] [Python ETL vs. ETL Tools][2]
- [[s.l.python]] [Python’s Data Classes a Data Engineer’s best friend][3]
- [[s.l.rust]] [Why you shouldn’t use Rust][4]
- [[s.l.python]] [[s.l.python.libs.sphinx]] [Auto Documenting a Python Project Using Sphinx][5]
- [[s.l.python]] [[s.l.python.libs.sphinx]] [Write Beautiful Python Documentation with Sphinx][6]
- [[s.apps.azure.devops]] [[s.apps.azure.test-plans]] [Automated and Manual Testing with Azure Test Plan][7]
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

[1]: https://medium.com/nerd-for-tech/python-is-a-bad-programming-language-2ab73b0bda5
[2]: https://towardsdatascience.com/python-etl-vs-etl-tools-9709171c9e58
[3]: https://medium.com/analytics-and-data/pythons-data-classes-a-data-engineer-s-best-friend-173617ee0941
[4]: https://preettheman.medium.com/why-you-shouldnt-use-rust-e55b6607e711
[5]: https://betterprogramming.pub/auto-documenting-a-python-project-using-sphinx-8878f9ddc6e9
[6]: https://python.plainenglish.io/documentation-with-sphinx-dd86bedb7512
[7]: https://youtu.be/LF0hmSysWCg
[8]: https://docs.python.org/3/library/profile.html
