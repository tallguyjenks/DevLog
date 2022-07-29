

## Scope Resolution Operator

in the class we may declare member functions but if there is a lot of logic we don't want to crowd the class so we may take advantage of the `Scope Resolution Operator`: `::`. Similar to how `R` code uses `::` to access functions from specific packages. We do this by putting a Functions in the class declaration and then the Functions below which houses all the logic:

```cpp
void   SetTime(int timeRunSecs);       // Time run in seconds

}; // end of the class declaration

// "RunnerInfo::" means SetTime is a RunnerInfo member function
void RunnerInfo::SetTime(int timeRunSecs) {
   timeRun = timeRunSecs;  // timeRun refers to data member
   return;
}
```

If a member function has the word `const` after its declaration like: 

```cpp
double GetSpeedMph() const;            // Speed in miles/hour
```

from the Example above, then this means that this member function cannot change the value of any data member or else an error is thrown.
