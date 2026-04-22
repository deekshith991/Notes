
# Make - to build the project

- Compiles only the files that are changed not everything.
- supports wildcards and regex
- % -> wildcard.
- @ -> make special value it is the leftpart of **:**
  Eg: @ = %.o line 22
- ^ -> make special value it is the rightpart of **:**
  Eg: ^= %.c  line 22

## variables

```makefile
CC = gcc
INCDIR = -I.
OPT = -00
CFLAGS = -Wall -Wextra -g ${INCDIR} ${OPT}

# generic regex based rule
%.o : %.c
  ${CC} ${CFLAGS} -c -o $@ $^
```

- CC     ->is a variable that defines the compiler that we are using.
- INCDIR -> include folder that containt the defination.
             -I for include DIR argument . (or) ./ (or) {path} for the include files.
- OPT    -> for level of optimizations.
- CFLAGS -> for additional flags.

## complicated project
- this project will consist of include lib etc
```makefile

CC = gcc
INCDIR = -I./include/
CODEDIRS= . lib

DEPFLAGS = -MP -MD 
OPT = -00
CFLAGS = -Wall -Wextra -g $( foreach D,${INCDIR}, -I${D}) ${OPT} ${DEPFLAGS} #for loop

```

- DEPFLAGS -> used for generating dependecy files to check if dependencies have changed or not. it work with make.

