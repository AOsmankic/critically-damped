# General Tools
Tools that just make life easier


## Grep
A linux command line tool that filters out console output containing a given key word

Usage: `{command} | grep {str}`
Description: finds any lines from the output of {command} with the token {str} in it

Usage: `{command} | grep {str} -A{num}`
Description: Finds the line that contains {str} and displays {num - 1} lines after it

Usage: `{command} | grep {str} -B{num}`
Description: Finds the line that contains {str} and displays {num - 1} lines Before it