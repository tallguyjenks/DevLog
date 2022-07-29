
## Error-Proof Your Variables

```bash
export somedir="/home/user/somedir"
rm -rf /$somedir
# IF $somedir is unset or null then it will wipe out root "/"
#
# The failsafe
rm -rf /${somedir:?}
```

## Skip the Long if-else Statements

```bash
# INSTEAD of

#!/bin/bash
rsync -azP somefile server1:/tmp
if [ ! $? -eq 0 ]
then
  echo "error with rsync"
  exit 1
fi
echo "continuing next step"

# USE THIS

[ ! $? -eq 0 ] && { echo "error with rsync"; exit 1; } 
```

The `{}` braces are basically your `then` statements separated by `;`.

## Don’t Rely on Passing Arguments

```bash
# Instead of assuming the order of the values was provided as desired like `args` in python
# Rely on `"${@}"1 like kwargs in python

#!/bin/bash
## reads in name and age, has boolean flag "--reset" which changes age to be 1
source functions.sh
get_params "${@}"

# Each of thuese results in the below

./main.sh --name joe --reset --age 25
./main.sh --age 25 --name joe --reset

#> NAME="joe"
#> AGE="25"
#> RESET="true"
```

## Easily Check Your Positional Arguments

```bash
name=${1:?"Error: parameter missing Name"}
age=${2:?"Error: parameter missing Age"}

./main joe
#> Error: parameter missing Age
```

## Create a Default Value for a Variable

```bash
echo "enter your name"
read name
name=${name:-Unknown}
```

If a user enters blank, your $name will be set to Unknown. The dash after the colon provides a default fallback value.
