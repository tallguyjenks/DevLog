

### Vector Equality

in the above example in [[import.software.language.cpp.include-vector#Vector copying]], if one were to change the values in some of the elements in `salePrices` and then perform an equality check `==` then the vector will compare element to element through the whole vector and return a boolean result.

```cpp
// Update salePrices. Note: does not affect origPrices
salePrices.at(2) = 27;
salePrices.at(3) = 35;

salePrices == origPrices; // because of above they are no longer equal
						  // or identical, result is false
```
