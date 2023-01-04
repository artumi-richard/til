# Jest: Fix no window object errors

You need to install a package

```
npm install jsdom
```

And then you need to tell each test file to use it by adding a comment
at the top of the file that looks like this:


```
/**
 * @jest-environment jsdom
 **/
```
