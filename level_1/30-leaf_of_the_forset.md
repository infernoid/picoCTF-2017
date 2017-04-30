## Leaf of the Forest [30 Points]

We found an even bigger directory tree hiding a flag starting at /problems/db39b5c002d8445dc6d2bbf49a8ccc37. It would be impossible to find the file named flag manually...

**Hints:**

- Is there a search function in Linux? Like if I wanted to 'find' something...

**Solution:**

```
$ ssh shell2017.picoctf.com
$ cd /problems/db39b5c002d8445dc6d2bbf49a8ccc37
$ find -name flag
./forest/treeada53a/trunkb393/trunkb8ea/trunka3c4/trunk639d/trunk324e/trunk0bf8/trunkf462/branchd463/flag
$ cat ./forest/treeada53a/trunkb393/trunkb8ea/trunka3c4/trunk639d/trunk324e/trunk0bf8/trunkf462/branchd463/flag
c99501b0fe95402ed1c9191102fe1b68
```

**Flag:** c99501b0fe95402ed1c9191102fe1b68
