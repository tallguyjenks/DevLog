- **Meta:**
	- [[Queries]]
	- [[Templates]]
	- [[TODO]] | [[DOING]] | [[DONE]] | [[NOW]] | [[LATER]]
- **Tags:**
	- #language | #library | #tools
	- **Emoji tags**
		- #star | Star
		- #idea | Idea
		- #documentation | Documentation
- **TOP OF MIND**
	- [[Python]]
	- [[VSCode]]
	- [[Azure DevOps]]
-
  ```python
  	  import yaml
  	  with open("example.yaml") as fp:
  	      data = fp.read()
  	  parsed = yaml.safe_load_all(data)  # parsed is a generator
  	  ```