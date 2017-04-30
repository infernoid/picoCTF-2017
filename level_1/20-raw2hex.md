## Raw2Hex [20 Points]

This program just prints a flag in raw form. All we need to do is convert the output to hex and we have it! CLI yourself to /problems/608e5f8b55c005ae6bc4ff13393c9c23 and turn that Raw2Hex!

**Hints:**

- Google is always very helpful in these circumstances. In this case, you should be looking for an easy solution.

**Solution:**

```
$ ssh shell2017.picoctf.com
$ cd /problems/608e5f8b55c005ae6bc4ff13393c9c23

$ ls -al
total 56
drwxr-xr-x   2 root       root       4096 Mar 31 07:41 .
drwxr-x--x 573 root       root      36864 Apr 16 23:31 ..
-r--r-----   1 hacksports raw2hex_1    33 Mar 31 07:41 flag
-rwxr-sr-x   1 hacksports raw2hex_1  7848 Mar 31 07:41 raw2hex

$ ./raw2hex
The flag is:=��C]Y��+��=|D�2

$ ./raw2hex | python -c 'import sys; print sys.stdin.readline()[12:].encode("hex")'
3dacd3435d59a4862b9ff83d7c44cd32
```

**Flag:** 3dacd3435d59a4862b9ff83d7c44cd32
