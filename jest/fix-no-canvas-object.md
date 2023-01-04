# Jest: Fix no canvas object

When running jest if it needs to use a <canvas> element then you need
to install a package:

```
npm install canvas
```

That seems to be it, jest will see it, and use it. 
