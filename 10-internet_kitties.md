## Internet Kitties [10 Points]

I was told there was something at IP shell2017.picoctf.com with port 12275. How do I get there? Do I need a ship for the port?

**Hints:**

- Look at using the netcat (nc) command!
- To figure out how to use it, you can run "man nc" or "nc -h" on the shell, or search for it on the interwebz

**Solution:**

```
$ nc shell2017.picoctf.com 12275
Yay! You made it!
Take a flag!
1e1ccf22b278d35b1977c76bb66c5e30
```

**Flag:** 1e1ccf22b278d35b1977c76bb66c5e30
