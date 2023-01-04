# Jest: Fix no indexeddb object

The test environment doesn't come with an indexeddb object, so code
that uses that can't be tested without installing something to fake
it:

```
npm install fake-indexeddb
```

Then in the test file we need to include it at the top
```
require("fake-indexeddb/auto");
```

