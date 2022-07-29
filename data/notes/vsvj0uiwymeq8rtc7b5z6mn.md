

### Accessors

Accessors can let the user access the values of the private data members:

> Accessor functions usually are defined as const, to enforce that they do not change data members. The keyword **const** after a member function's declaration and definition causes the compiler to report an error if the function modifies a data member. **<u>If a const member function calls another member function, that function must also be const.</u>**

```cpp
int  GetPlayer1PlayA() const;        // Accessor
int  GameInfo::GetPlayer1PlayA() const {
   return player1PlayA;
}
```
