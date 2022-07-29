

## VS Code Stanard Variables

- <https://code.visualstudio.com/docs/editor/userdefinedsnippets>

## Template Variables

Dendron supports various template variables.

- For inserting the current date and time:
  - CURRENT_YEAR: The current year
  - CURRENT_MONTH: The month as two digits (example '02')
  - CURRENT_DAY: The day of the month as two digits (example '08')
  - CURRENT_HOUR: The current hour in 24-hour clock format
  - CURRENT_MINUTE: The current minute as two digits
  - CURRENT_SECOND: The current second as two digits

### VS Code default variables

The following variables can be used:

- `TM_SELECTED_TEXT` The currently selected text or the empty string
- `TM_CURRENT_LINE` The contents of the current line
- `TM_CURRENT_WORD` The contents of the word under cursor or the empty string
- `TM_LINE_INDEX` The zero-index based line number
- `TM_LINE_NUMBER` The one-index based line number
- `TM_FILENAME` The filename of the current document
- `TM_FILENAME_BASE` The filename of the current document without its extensions
- `TM_DIRECTORY` The directory of the current document
- `TM_FILEPATH` The full file path of the current document
- `RELATIVE_FILEPATH` The relative (to the opened workspace or folder) file path of the current document
- `CLIPBOARD` The contents of your clipboard
- `WORKSPACE_NAME` The name of the opened workspace or folder
- `WORKSPACE_FOLDER` The path of the opened workspace or folder

For inserting the current date and time:

- `CURRENT_YEAR` The current year
- `CURRENT_YEAR_SHORT` The current year's last two digits
- `CURRENT_MONTH` The month as two digits (example '02')
- `CURRENT_MONTH_NAME` The full name of the month (example 'July')
- `CURRENT_MONTH_NAME_SHORT` The short name of the month (example 'Jul')
- `CURRENT_DATE` The day of the month as two digits (example '08')
- `CURRENT_DAY_NAME` The name of day (example 'Monday')
- `CURRENT_DAY_NAME_SHORT` The short name of the day (example 'Mon')
- `CURRENT_HOUR` The current hour in 24-hour clock format
- `CURRENT_MINUTE` The current minute as two digits
- `CURRENT_SECOND` The current second as two digits
- `CURRENT_SECONDS_UNIX` The number of seconds since the Unix epoch

### Example

```md
Today is {{ CURRENT_YEAR }}.{{ CURRENT_MONTH }}.{{ CURRENT_DAY }},
```

output:

> Today is 2022.01.04

## Template Variable replacement

For replacing the standard variables inside the dendron template files

<https://wiki.dendron.so/notes/GelEQPZrSgr3CK9y10Nrg/#template-variables>


## VSCode Snippet Tricks

1. You can set a default value for a variable by using a colon (:).

Example:

- The DUE: property in the below snippet defaults to the current current month, date, hour but can be edited fairly quick

```json
"TODO": {
   "prefix": "stodo",
   "body": [
    "- [ ] ${1:Enter Task}",
    "- **CAPTURED:**        ${CURRENT_YEAR}-${CURRENT_MONTH}-${CURRENT_DATE}T${CURRENT_HOUR}:${CURRENT_MINUTE}:${CURRENT_SECOND}-08:00",
    "- **DUE:**             ${CURRENT_YEAR}-${2:${CURRENT_MONTH}}-${3:${CURRENT_DATE}}T${4:${CURRENT_HOUR}}:${5:${CURRENT_MINUTE}}:00-08:00",
    "- **PRIORITY:**        ${6|HIGH,MEDIUM,LOW|}",
    "- **STATUS:**          ${7|TODO,WAITING,IN PROGRESS,DONE|}",
    "- **NOTES:**           ",
    "    - $0",
    ],
    "description": "Capture new TODO"
}
```

1. You can set dropdown values for a variable using a pipe (|).

Example:

```json
"Context Switch": {
   "prefix": "scontext",
   "body": [
    "- **TYPE:**          ${1|COMMS,SUPPORT,RESEARCH,MEETING,DEVELOPMENT,TESTING,VALIDATION,CI/CD,PROJECT MGMT,CONSULTING,DOCUMENTATION,ADMINISTRATION,TRAINING,BREAK|}",
    "- **PROJECT:**       ${2|PROJ1,PROJ2|}",
    "- **TOOLS:**         ${3|N/A,PYTHON,AZURE,POWER APPS,POWER AUTOMATE,POWER BI,SHAREPOINT,DENDRON|}",
    "- **START:**         ${CURRENT_YEAR}-${CURRENT_MONTH}-${CURRENT_DATE}T${CURRENT_HOUR}:{$CURRENT_MINUTE}:${CURRENT_SECOND}-08:00",
    "- **END:**           ",
    "- **DURATION:**      ",
    "- **NOTES:**         ",
    "    - $0",
    "---"
    ],
    "description": "Capture new context switch"
}
```
