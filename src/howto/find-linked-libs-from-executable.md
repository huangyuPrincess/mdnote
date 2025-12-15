To check the libraries linked to an executable, use command-line tools appropriate for dynamic and static libraries, which vary by operating system.

#### For Dynamic Libraries
##### Linux: Use the ldd command followed by the executable name to list dynamic dependencies.
```
ldd <executable_filename>
```

##### macOS: Use the otool -L command.
```
otool -L <executable_filename>
```

##### Windows: Use the dumpbin /dependents command (part of Visual Studio tools) or a graphical tool like Dependency Walker.
```
dumpbin /dependents <executable_filename> 
```

#### For Static Libraries
It is much harder to determine statically linked libraries from the final executable because the library's contents are merged directly into the binary at link time, and library names are typically discarded. 

You can use tools like nm or objdump to inspect the symbols (function names) within the executable, which might provide hints about the libraries used, but not a definitive list.
```
nm <executable_filename>
```
If you have the source code, generating a map file during compilation can provide a list of linked static libraries. 
