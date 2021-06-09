---
title: tqdm
tags: library
---

- [GitHub Repo](https://github.com/tqdm/tqdm) | [Docs](https://tqdm.github.io/) | [Calm Code tqdm](https://calmcode.io/tqdm/making-a-progress-bar.html)
- Wrap an itterable in the function for an aesthetic progress bar:
	-
	  ```python
	  import this
	  import tqdm
	  
	  for i in tqdm.tqdm(range(100), desc=" first loop"):
	      time.sleep(0.02)
	  
	  for i in tqdm.tqdm(range(100), desc=" second loop"):
	      time.sleep(0.02)
	  
	  print("done!")
	  ```
	-