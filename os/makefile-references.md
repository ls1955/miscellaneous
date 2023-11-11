# Reference
```bash
# Given this statement
$@ : name of target
$< : name of source

main.o: main.cpp
    g++ $(GPPPARAMS) -o $@ -c $<
# $@ == main.o
# $< == main.cpp
```

