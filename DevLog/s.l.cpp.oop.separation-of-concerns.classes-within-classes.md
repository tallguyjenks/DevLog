---
id: fq75676y72z6f37z0jw9nr6
title: Classes within Classes
desc: ''
updated: 1641372091857
created: 1641372091857
---


### Classes Within Classes

`TeamPerson.h`

```cpp
#ifndef TEAMPERSON_H
#define TEAMPERSON_H

#include <string>
using namespace std;

class TeamPerson {
   public:
      void   SetFullName(string firstAndLastName);
      void   SetAgeYears(int ageInYears);
      string GetFullName() const;
      int    GetAgeYears() const;
      void   Print() const;

   private:
      string fullName;
      int    ageYears;
};

#endif
```

`TeamPerson.cpp`

```cpp
#include <iostream>
#include <string>
using namespace std;

#include "TeamPerson.h"

void TeamPerson::SetFullName(string firstAndLastName) {
   fullName = firstAndLastName;
   return;
}

void TeamPerson::SetAgeYears(int ageInYears) {
   ageYears = ageInYears;
   return;
}

string TeamPerson::GetFullName() const {
   return fullName;
}

int TeamPerson::GetAgeYears() const {
   return ageYears;
}

void TeamPerson::Print() const {
   cout << "Full name: "   << fullName << endl;
   cout << "Age (years): " << ageYears << endl;
}
```

`SoccerTeam.h`

```cpp
#ifndef SOCCERTEAM_H
#define SOCCERTEAM_H

#include "TeamPerson.h"

class SoccerTeam {
   public:
      void SetHeadCoach(TeamPerson teamPerson);
      void SetAssistantCoach (TeamPerson teamPerson);

      TeamPerson GetHeadCoach() const;
      TeamPerson GetAssistantCoach() const;

      void Print() const;

   private:
      TeamPerson headCoach;
      TeamPerson assistantCoach;
      // Players omitted for brevity
};

#endif
```

`SoccerTeam.cpp`

```cpp
#include <iostream>
using namespace std;

#include "TeamPerson.h"
#include "SoccerTeam.h"

void SoccerTeam::SetHeadCoach(TeamPerson teamPerson) {
   headCoach = teamPerson;
   return;
}

void SoccerTeam::SetAssistantCoach(TeamPerson teamPerson) {
   assistantCoach = teamPerson;
   return;
}

TeamPerson SoccerTeam::GetHeadCoach() const {
   return headCoach;
}

TeamPerson SoccerTeam::GetAssistantCoach() const {
   return assistantCoach;
}

void SoccerTeam::Print() const {
   cout << "HEAD COACH: " << endl;
   headCoach.Print();
   cout << endl;

   cout << "ASSISTANT COACH: " << endl;
   assistantCoach.Print();
   cout << endl;
   return;
}
```

`main.cpp`

```cpp
#include <iostream>
using namespace std;

#include "SoccerTeam.h"
#include "TeamPerson.h"

int main() {
   SoccerTeam teamCalifornia;
   TeamPerson headCoach;
   TeamPerson asstCoach;

   headCoach.SetFullName("Mark Miwerds");
   headCoach.SetAgeYears(42);
   teamCalifornia.SetHeadCoach(headCoach);

   asstCoach.SetFullName("Stanley Lee");
   asstCoach.SetAgeYears(30);
   teamCalifornia.SetAssistantCoach(asstCoach);

   teamCalifornia.Print();

   return 0;
}
```
