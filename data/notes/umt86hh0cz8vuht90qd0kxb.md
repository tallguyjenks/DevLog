

## Information

- <https://realpython.com/command-line-interfaces-python-argparse/>
- The Python [[argparse|import.argparse]] library:
  - Allows the use of positional arguments
  - Allows the customization of the prefix chars
  - Supports variable numbers of parameters for a single option
  - Supports subcommands (A main command line parser can use other command line parsers depending on some arguments.)

## Examples

```python
# myls.py
# Import the argparse library
import argparse

import os
import sys

my_parser = argparse.ArgumentParser(prog='myls',
								  usage='%(prog)s [options] path',
								  description='List the content of a folder')

my_parser.version = '1.0'
my_parser.add_argument('-a',
					 action='store',
					 choices=['head', 'tail'],
					 help='set the user choice to head or tail')
my_parser.add_argument('-b',
					 action='store_const',
					 const=42,
					 type=int)
my_parser.add_argument('-c', action='store_true')
my_parser.add_argument('-d', action='store_false')
my_parser.add_argument('-e', action='append')
my_parser.add_argument('-f',
					 action='append_const',
					 const=42,
					 type=int)
my_parser.add_argument('-g', action='count')
my_parser.add_argument('-i', action='help')
my_parser.add_argument('-j', action='version')
my_parser.add_argument('-k',
					 action='store',
					 type=int,
					 choices=range(1, 5))

my_group = my_parser.add_mutually_exclusive_group(required=True)

my_group.add_argument('-v', '--verbose', action='store_true')
my_group.add_argument('-s', '--silent', action='store_true')

# Add the arguments
my_parser.add_argument('Path',
					 metavar='path',
					 type=str,
					 help='the path to list')

# Execute the parse_args() method
args = my_parser.parse_args()

input_path = args.Path

if not os.path.isdir(input_path):
  print('The path specified does not exist')
  sys.exit()

print('\n'.join(os.listdir(input_path)))
```
