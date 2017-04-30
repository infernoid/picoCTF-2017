## Bash Loop [40 Points]

We found a program that is hiding a flag but requires you to guess the number it is thinking of. Chances are Linux has an easy way to try all the numbers... Go to /problems/e3f1970eb419b3aa32788a43ec91ef08 and try it out!

**Hints:**

- Either use SSH or use the Web Shell to get onto the shell server and navigate to the correct directory. Then do a quick Google search on 'bash loops'. You may need to use grep to filter out the responses as well!

**Solution:**

```
$ ssh shell2017.picoctf.com
$ cd /problems/e3f1970eb419b3aa32788a43ec91ef08

$ ls -al
total 60
drwxr-xr-x   2 root       root         4096 Mar 31 08:01 .
drwxr-x--x 573 root       root        36864 Apr 16 23:31 ..
-rwxr-sr-x   1 hacksports bash-loop_5  8216 Mar 31 08:01 bashloop
-r--r-----   1 hacksports bash-loop_5    33 Mar 31 08:01 flag

$ ./bashloop
What number am I thinking of? It is between 0 and 4096

$ for i in {0..4096}; do ./bashloop $i; done | grep flag
Yay! That's the number! Here be the flag: 9960332950d7db392f97f29dee04f4ee

```

**Flag:** 9960332950d7db392f97f29dee04f4ee
