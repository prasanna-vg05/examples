# Static Linking

## `/static` Static Linking Example

To statically link your program, first compile the source files and then link them together:

```sh
    gcc -c main.c mylib.c
    
    gcc main.o mylib.o -o main
```

This produces an executable named `main` with static linking.

## `/dynamic` Dynamic Linking Example

To dynamically link your program, compile the source files as position-independent code and create a shared library:

```sh
    gcc -fPIC -shared mylib.c -o usr/libmylib1.so

    gcc main.c -I. -Lusr -lmylib1 -o main
    
    export LD_LIBRARY_PATH=$PWD/usr
    
    ./main
```


