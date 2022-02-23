---
id: mgjIWXOWt7eqdFpguUwlv
title: CI CD
desc: ''
updated: 1645579151868
created: 1641440364153
---

`C`ontinuous `I`ntegration - `C`ontinuous `D`evelopment

- Source
  - Version control ([[cli.cmd.git]])
- Build (Should be Toggle-able for when you dont want something to run through the gamut)
  - Compile Source and Dependencies
  - Unit tests
  - Coverage > 90%
- Test (Should be Toggle-able for when you dont want something to run through the gamut)
  - Integration tests 
    - If you have an [[terms.api]] then test a POST request followed by a GET request
    - If you have external service dependencies, test them too
    - In essence, test the core functionality of your app so that changed behavior will easily show up
- Prod Environment
  - 1 Box (have incremental roll out to a single machine or a small fraction of them so impacts are smaller and more readily identified and rolled back)
