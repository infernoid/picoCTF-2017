## Leaf of the Tree [20 Points]

We found this annoyingly named directory tree starting at /problems/4052472b84e355d1e1a42f5899fe0e76. It would be pretty lame to type out all of those directory names but maybe there is something in there worth finding? And maybe we dont need to type out all those names...? Follow the trunk, using cat and ls!

**Hints**

- Tab completion is a wonderful, wonderful thing

**Solution:**

```
$ ssh shell2017.picoctf.com
$ cd /problems/4052472b84e355d1e1a42f5899fe0e76
$ find -name flag
$ cat ./trunk/trunkef9b/trunk99e1/trunk54f4/trunk61be/trunk89be/trunk87bf/trunkb252/flag
aae8c400f845fd47fdbb6a77ba027771
```

**Flag:** aae8c400f845fd47fdbb6a77ba027771
