```
Given:
#bad
BashOperator(
    bash_command='bash your_script.sh'
)

If Jinja Template error, try include a space after `your_script.sh`.
...yep.

#good
BashOperator(
    bash_command='bash your_script.sh '
)
```