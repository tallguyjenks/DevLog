

## Projects

**Question Extractor Written In Bash**

```shell
if [[ -e $1 ]]
then
filename="Questions $1"
count=$(grep -Fc '**Q**' "$1")
report="$count Questions extracted from $filename"
printf "# $report \n \n" > "./$filename"
grep -Fn '**Q**' "$1" | sed -e 's/\*\*Q:*\*\*:*//g' | sed -e 's/^/- /' >> "$filename"
echo $report
else
echo Provide a file as an argument
fi
```

This script will take a file as an input argument and then any lines it finds the text `**Q**` on it will extract into a list of questions in a new file called `questions_<input file name>` and also report in the CLI how many questions were extracted
