```shell
javac -h . <.java> # compile header from .java file
# compile .so from .cpp
g++ -fPIC -I"$JAVA_HOME/include" -I"$JAVA_HOME/include/linux" -shared -o <.so> <.cpp>
javap -s -p <class> # check class's methods signature
java -Djava.library.path=. <class> # run .java (after everything is set)
```
