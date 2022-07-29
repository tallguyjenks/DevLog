

## srand

The pseudo-random number generator is initialized using the argument passed as seed.

For every different seed value used in a call to `srand`, the pseudo-random number generator can be expected to generate a different succession of results in the subsequent calls to `rand`.

Two different initializations with the same seed will generate the same succession of results in subsequent calls to `rand`.

If seed is set to 1, the generator is reinitialized to its initial value and produces the same values as before any call to rand or `srand`.

In order to generate random-like numbers, `srand` is usually initialized to some distinctive runtime value, like the value returned by function time (declared in header `<ctime>`). This is distinctive enough for most trivial randomization needs.

```cpp
#include <iostream>
#include <cstdlib>
#include <ctime>

int main(int argc, const char * argv[]) {
     printf ("First number: %d\n", rand()%100);
    
     srand (time(0));
    
     printf ("Random number: %d\n", rand()%100);
     srand (1);
     printf ("Again the first number: %d\n", rand()%100);

    return 0;
}
```
