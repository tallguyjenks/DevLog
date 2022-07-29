

## Specifying dependency targets

```make
final_target: sub_target final_target.c
	Recipe_to_create_final_target

sub_target: sub_target.c
	Recipe_to_create_sub_target
```

```make
say_hello:
	echo "Hello World"
```

- `say_hello:` == _The Target_
- _prerequisites_ or _dependencies_ follow the target
- `echo "Hello World"` == _The Recipe_
- The _target_, _prerequisites_, and _recipes_ together make a _rule_.
- **Suppress command** text and only show output with `@` like `@echo "hello world"`

```make
say_hello:
	  @echo "Hello World"

generate:
	  @echo "Creating empty text files..."
	  touch file-{1..10}.txt

clean:
	  @echo "Cleaning up..."
	  rm *.txt
```

- This will only run the `say_hello` function because it's the default target ( the first thing )
- to hard code the default target, include this at beginning of file: `.DEFAULT_GOAL := generate`
  - To instead run all targets the target `all` is used to call all other targets

```make
all: say_hello generate

say_hello:
	  @echo "Hello World"

generate:
	  @echo "Creating empty text files..."
	  touch file-{1..10}.txt

clean:
	  @echo "Cleaning up..."
	  rm *.txt
```
