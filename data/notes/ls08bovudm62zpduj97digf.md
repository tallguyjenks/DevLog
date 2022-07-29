

## Resources

- [Python Asynchronous Programming - AsyncIO & Async/Await](https://youtu.be/t5Bo1Je9EmE)

## Example

```python
import asyncio

async def main():
    await asyncio.sleep(0.5)
    print('Bryan')
    await asyncio.sleep(0.5)

asyncio.run(main())

#>>> Bryan
```

### async

```python
import asyncio

async def main():
    print('Bryan')

asyncio.run(main())
```

### await

```python
import asyncio

async def main():
    await asyncio.sleep(0.5)
    print('Bryan')
    await asyncio.sleep(0.5)

asyncio.run(main())

#>>> Bryan
```

### gather

Run several functions in parallel

```python
import asyncio

async def main0():
    print('Bryan')

async def main1():
    print('John')

async def main2():
    print('Jane')

async def testing():
    asyncio.gather(
            main0(),
            main1(),
            main2()
    )

asyncio.run(testing())
```

### Structure parallelism and sequential execution elegantly

```python
import asyncio

async def run_sequence(*functions: Awaitable[Any]) -> None:
    for function in functions:
        await function

async def run_parallel(*functions: Awaitable[Any]) -> None:
    await asyncio.gather(*functions)

```

- Reference:
  - [[how-to-easily-do-asynchronous-programming-with-asyncio-in-python|r.+.2021.12.21.how-to-easily-do-asynchronous-programming-with-asyncio-in-python]]
