---
id: cqfweun5b1vtfp28f4p1o40
title: Awk
desc: ''
updated: 1641097235338
created: 1641097193050
---


```bash
#!/usr/bin/env bash

#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#
echo "=====Grab a field====="
read
echo "hello world this is Bryan" | awk '{print $1,$5}'
read
#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#
echo "=====Grab a column====="
read

echo "ajay manager account 45000
sunil clerk account 25000
varun manager sales 50000
amit manager account 47000
tarun peon sales 15000
deepak clerk sales 23000
sunil peon sales 13000
satvik director purchase 80000" | awk '{print}' 
read

echo "ajay manager account 45000
sunil clerk account 25000
varun manager sales 50000
amit manager account 47000
tarun peon sales 15000
deepak clerk sales 23000
sunil peon sales 13000
satvik director purchase 80000" | awk '{print $4}' 
read

#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#
echo "=====Selectively output fields====="
read

echo "ajay manager account 45000
sunil clerk account 25000
varun manager sales 50000
amit manager account 47000
tarun peon sales 15000
deepak clerk sales 23000
sunil peon sales 13000
satvik director purchase 80000" | awk '/manager/ {print}'
read

#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#
echo "=====Variables====="
echo "\$0 -- The whole line"
read
echo "Hello World" | awk '{print $0}'
read
echo "NR -- The Number of Records"
read

echo "ajay manager account 45000
sunil clerk account 25000
varun manager sales 50000
amit manager account 47000
tarun peon sales 15000
deepak clerk sales 23000
sunil peon sales 13000
satvik director purchase 80000" | awk '{print NR}'
read

echo "ajay manager account 45000
sunil clerk account 25000
varun manager sales 50000
amit manager account 47000
tarun peon sales 15000
deepak clerk sales 23000
sunil peon sales 13000
satvik director purchase 80000" | awk '{print $NR}'
read

echo "ajay manager account 45000
sunil clerk account 25000
varun manager sales 50000
amit manager account 47000
tarun peon sales 15000
deepak clerk sales 23000
sunil peon sales 13000
satvik director purchase 80000" | awk '{print $0}'
read

echo "NF -- Number of Fields"
read

echo "ajay manager account 45000
sunil clerk account 25000
varun manager sales 50000
amit manager account 47000
tarun peon sales 15000
deepak clerk sales 23000
sunil peon sales 13000
satvik director purchase 80000" | awk '{print NF}'
read

echo "ajay manager account 45000
sunil clerk account 25000
varun manager sales 50000
amit manager account 47000
tarun peon sales 15000
deepak clerk sales 23000
sunil peon sales 13000
satvik director purchase 80000" | awk '{print $NF}' 
read

echo "ajay manager account 45000
sunil clerk account 25000
varun manager sales 50000
amit manager account 47000
tarun peon sales 15000
deepak clerk sales 23000
sunil peon sales 13000
satvik director purchase 80000" | awk '{print $1,NF}' 
read

#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#
echo "=====Format some output====="
read

echo "ajay manager account 45000
sunil clerk account 25000
varun manager sales 50000
amit manager account 47000
tarun peon sales 15000
deepak clerk sales 23000
sunil peon sales 13000
satvik director purchase 80000" | awk '{print NR " - " $1}'
read

#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#
echo "=====BEGIN and END=====

BEGIN and END are special conditions that only get triggered once per run

BEGIN gets triggered before processing any line
END gets triggered after all lines have been processed"
read

echo "Using BEGIN on the data set:

ajay manager account 45000
sunil clerk account 25000
varun manager sales 50000
amit manager account 47000
tarun peon sales 15000
deepak clerk sales 23000
sunil peon sales 13000
satvik director purchase 80000"
read

echo "ajay manager account 45000
sunil clerk account 25000
varun manager sales 50000
amit manager account 47000
tarun peon sales 15000
deepak clerk sales 23000
sunil peon sales 13000
satvik director purchase 80000" | awk 'BEGIN {print NR}' 
read

echo "Using END on the data set:"
read

echo "ajay manager account 45000
sunil clerk account 25000
varun manager sales 50000
amit manager account 47000
tarun peon sales 15000
deepak clerk sales 23000
sunil peon sales 13000
satvik director purchase 80000" | awk 'END {print NR}'
read

#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#===#
echo "=====Setting a delimiter====="
read

echo "ajay/manager/account/45000
sunil/clerk/account/25000
varun/manager/sales/50000
amit/manager/account/47000
tarun/peon/sales/15000
deepak/clerk/sales/23000
sunil/peon/sales/13000
satvik/director/purchase/80000" | awk -F/ '{print $1,$4}' 
# -F can take regex '[,-/]' to determine the delimiter, a `/` in this case
read
```
