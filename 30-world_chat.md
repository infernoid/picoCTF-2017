## WorldChat [30 Points]

We think someone is trying to transmit a flag over WorldChat. Unfortunately, there are so many other people talking that we can't really keep track of what is going on! Go see if you can find the messenger at shell2017.picoctf.com:38798. Remember to use Ctrl-C to cut the connection if it overwhelms you!

**Hints:**

- There are cool command line tools that can filter out lines with specific keywords in them. Check out 'grep'! You can use the '|' character to put all the output into another process or command (like the grep process)

**Solution:**

```
$ nc shell2017.picoctf.com 38798 | grep flag
15:27:14 noihazflag: Only us will never be able for the future of humanity
15:27:14 whatisflag: We will never be able for the future of humanity
15:27:14 ihazflag: your dad totally understands me and my pet sloth to create a self driving car
15:27:15 personwithflag: A silly panda totally understands me and my pet sloth to drink your milkshake
15:27:15 noihazflag: my homegirlz will never be able to create a self driving car
15:27:15 whatisflag: my parents will never be able to create a self driving car
15:27:16 flagperson: this is part 1/8 of the flag - 3572
15:27:16 ihazflag: that guy from that movie gives me hope to make a rasberry pie
15:27:16 personwithflag: We give me hope for the future of humanity
^C (Ctrl+C)

$ nc shell2017.picoctf.com 38798 | grep flagperson
15:30:26 flagperson: this is part 1/8 of the flag - 3572
15:30:29 flagperson: this is part 2/8 of the flag - dd03
15:30:32 flagperson: this is part 3/8 of the flag - 4e91
15:30:33 flagperson: this is part 4/8 of the flag - 5f49
15:30:37 flagperson: this is part 5/8 of the flag - 3120
15:30:43 flagperson: this is part 6/8 of the flag - 885d
15:30:43 flagperson: this is part 7/8 of the flag - 41d5
15:30:48 flagperson: this is part 8/8 of the flag - 46c7
^C (Ctrl+C)
```

**Flag:** 3572dd034e915f493120885d41d546c7
