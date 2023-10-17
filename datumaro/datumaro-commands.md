Although author pretty sure he won't need those commands, nor will he understand
those commands after that part-time jobs, here goes...

```bash
datum project create -o ./ # initialize something at current directory
datum source add -f yolo <dir> # add a dir to something 
datum transform -t rename <dir> -e "|<from>|<to>" # rename files in a dir to something
datum transform -t random_split <dir> -- --subset train:.7 --subset test:.3 # create another dir in a dir
```
