---
id: RUnu7V3wVzpsPhMW5k8Ie
title: Variables Aka Macros
desc: ''
updated: 1642708557481
created: 1642708537883
---

## Variable aka Macros

> are like variable replacement in makefiles

```make
# ==================
# USING VARIABLES (aka macros)
# ==================
# VARIABLENAME = VALUE OF VARIABLE
# they expand using the syntax $(VARIABLENAME)


TMP = tester1.txt
OUTPUT = tester2.txt

$(OUTPUT): $(TMP)
cat $(TMP) > $(OUTPUT)

$(TMP):
echo "this is a test" > $(TMP)
```
