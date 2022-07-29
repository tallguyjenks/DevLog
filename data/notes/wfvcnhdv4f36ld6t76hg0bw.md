

##### Get Opts In Bash

how to get flag options in a bash script

```bash
#  Documentation
a_flag=''
b_flag=''
files=''
verbose='false'

print_usage() {
	printf "Usage: ..."
}

while getopts 'abf:v' flag; do
	case "${flag}" in
		a) a_flag='true' ;;
		b) b_flag='true' ;;
		f) files="${OPTARG}" ;;
		v) verbose='true' ;;
		*) print_usage
		   exit 1 ;;
	esac
done
```

###### Documentation

- [SO Article](https://stackoverflow.com/questions/7069682/how-to-get-arguments-with-flags-in-bash#21128172)
