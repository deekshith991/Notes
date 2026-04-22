
## compile

**gcc -c file -o out**


IF include folder used: -I./include 
here ./include is path
## Shared library
**gcc -fPIC -share file -o libfile.so** for shared libraray 

here the shared libary need lib as prefix and .so as suffix

we also need to set load library to find the shared libraries
LD_LIBRARY_PATH = "./" 

