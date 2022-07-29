

- [GitHub Repo](https://github.com/tqdm/tqdm) \| [Docs](https://tqdm.github.io/) \| [Calm Code tqdm](https://calmcode.io/tqdm/making-a-progress-bar.html)
- Wrap an itterable in the function for an aesthetic progress bar:

```python
import this
import tqdm

for i in tqdm.tqdm(range(100), desc=" first loop"):
  time.sleep(0.02)

for i in tqdm.tqdm(range(100), desc=" second loop"):
  time.sleep(0.02)

print("done!")
```

- Nested Loops

```python
import this
import tqdm

for outer in tqdm.tqdm([10, 20, 30, 40, 50], desc=" outer", position=0):
  for inner in tqdm.tqdm(range(outer), desc=" inner loop", position=1, leave=False):
	  time.sleep(0.05)
print("done!")
```
