## What Is Web

Someone told me that some guy came up with the "World Wide Web", using "HTML" and "stuff". Can you help me figure out what that is? Website.

**Hints:**

- How can you figure out how the webpage is actually built?

**Solution:**

Look in the source code of the html, css and javascript

http://shell2017.picoctf.com:58191/
```
<!-- Cool! Look at me! This is an HTML file. It describes what each page contains in a format your browser can understand. -->
<!-- The first part of the flag (there are 3 parts) is 4eabea7c5b1 -->
<!-- What other types of files are there in a webpage? -->
```

http://shell2017.picoctf.com:58191/hacker.css
```
/*
This is the css file. It contains information on how to graphically display
the page. It is in a seperate file so that multiple pages can all use the same
one. This allows them all to be updated by changing just this one.
The second part of the flag is e8e0c84cc61
*/
```

http://shell2017.picoctf.com:58191/script.js
```
/* This is a javascript file. It contains code that runs locally in your
 * browser, although it has spread to a large number of other uses.
 *
 * The final part of the flag is 2a79d2dc833
 */
```

**Flag:** 4eabea7c5b1e8e0c84cc612a79d2dc833
