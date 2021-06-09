---
title: argparse
tags: library
---

- **Information**
	- https://realpython.com/command-line-interfaces-python-argparse/
- The Python [[argparse]] library:
	- Allows the use of positional arguments
	- Allows the customization of the prefix chars
	- Supports variable numbers of parameters for a single option
	- Supports subcommands (A main command line parser can use other command line parsers depending on some arguments.)
- **Examples**
	-
	  ```python
	  # myls.py
	  # Import the argparse library
	  import argparse
	  
	  import os
	  import sys
	  
	  my_parser = argparse.ArgumentParser(prog='myls',
	                                      usage='%(prog)s [options] path',
	                                      description='List the content of a folder')
	  
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
	-