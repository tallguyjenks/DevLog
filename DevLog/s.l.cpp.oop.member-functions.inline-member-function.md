---
id: lmfn0aby61x42y71w3fnndi
title: Inline Member Function
desc: ''
updated: 1641372338408
created: 1641372338408
---


## Inline Member Functions

Unlike the example you can put all the code for a member function in the class declaration. this is called an Inline Member Function, because the function is in the class declaration.

```cpp
class RunnerInfo {
   public:
      void   SetTime(int timeRunSecs) { // Here is the inline function
         timeRun = timeRunSecs;
      }
      void   SetDist(double distRunMiles);
      double GetSpeedMph() const;
   private:
      int    timeRun;
      double distRun;
};

void RunnerInfo::SetDist(double distRunMiles) {
   distRun = distRunMiles;

   return;
}
```
