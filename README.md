Unexpected behavior: file `bin/hello.ml` is linked in `doesntwork.exe`
even though `doesntwork.ml` only depends `Hellolib.Hello` whose source 
is `lib/hello.ml`.

Reproduction steps:
```
$ make
```

Output:
```
jbuilder runtest -f
         run alias bin/runtest
+ ./works.exe
Hello
+ ./doesntwork.exe
This shouldn't happen.
Hello
```

Expected output:
```
jbuilder runtest -f
         run alias bin/runtest
+ ./works.exe
Hello
+ ./doesntwork.exe
Hello
```
