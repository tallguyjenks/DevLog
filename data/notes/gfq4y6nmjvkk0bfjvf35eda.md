

## Inference rules

```make
# ==================
# USING INFERENCE RULES
# ==================

# $@ = prod.txt (if out of date)
# $* = prod (its the target with the .extention removed)
# $< = dep.txt (aka its the first dependancy)

# .SUFFIXES appends these to suffixes used for inference rules

.SUFFIXES: .tmp .txt

all: tester.txt

# make a .txt file using a .tmp file
# $< for the .tmp file
# $@ for the .txt file

# .inextension.outextension:
.tmp.txt:
cat $< > $*
```
