# Can't see console.log output in Jest

The default is that Jest would hide this output. 
You need to tell jest to do it explicitly.

You can either set it as a config in `package.json` so it has a
section that contains this:

```
    "jest": {
		"verbose": true,
		// -- other things here probably
    }
```

Or you can do it for a specific run by running with the command

```
npm run test -- --verbose=true
```


