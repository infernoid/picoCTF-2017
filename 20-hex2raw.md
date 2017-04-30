## Hex2Raw [20 Points]

This program requires some unprintable characters as input... But how do you print unprintable characters? CLI yourself to /problems/f8c6dddd9de81e356e316ec9789288cd and turn that Hex2Raw!

**Hints:**

- Google for easy techniques of getting raw output to command line. In this case, you should be looking for an easy solution.

**Solution:**

```
$ ssh shell2017.picoctf.com
$ cd /problems/f8c6dddd9de81e356e316ec9789288cd

$ ls -al
total 64
drwxr-xr-x   2 root       root       4096 Mar 31 07:42 .
drwxr-x--x 573 root       root      36864 Apr 16 23:31 ..
-r--r-----   1 hacksports hex2raw_8    33 Mar 31 07:42 flag
-rwxr-sr-x   1 hacksports hex2raw_8  9656 Mar 31 07:42 hex2raw
-r--r-----   1 hacksports hex2raw_8    33 Mar 31 07:42 input

$ ./hex2raw
Give me this in raw form (0x41 -> 'A'):
28fe16318f851d2f9de2b2ee90b55470

You gave me:
^C (Ctrl+C)

$ echo -ne "\x28\xfe\x16\x31\x8f\x85\x1d\x2f\x9d\xe2\xb2\xee\x90\xb5\x54\x70" | ./hex2raw
Give me this in raw form (0x41 -> 'A'):
28fe16318f851d2f9de2b2ee90b55470

You gave me:
28fe16318f851d2f9de2b2ee90b55470
Yay! That's what I wanted! Here be the flag:
88980fa0253a3b711d54d64a94b1646c
```

**Flag:** 88980fa0253a3b711d54d64a94b1646c
