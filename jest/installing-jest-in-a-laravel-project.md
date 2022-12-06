# Installing Jest in a Laravel project

First you need to install it with npm

```bash
npm install --save-dev jest
```

The `--save-dev` option means that the package will appear in the 
devDependencies, as opposed to if it was `--save-prod` which would
save to the "dependencies"

This means we now have jest. We want to run it so we have to update
our package.json

We need the scripts section to contain this:

```json
        "test": "jest"
```
So you'll have something like this:

```json

    "scripts": {
        "dev": "npm run development",
        "development": "mix",
        "watch": "mix watch",
        "watch-poll": "mix watch -- --watch-options-poll=1000",
        "hot": "mix watch --hot",
        "prod": "npm run production",
        "production": "mix --production",
        "test": "jest"
    },
```

You also need to add the bootstrap script that already appears in
`resources/js/bootstrap.js` to the jest config, which also goes in
package.json, and looks like this: 

```json
    "jest": {
        "setupFiles": [
            "./resources/js/bootstrap.js"
        ]
    }
```


Then you can create a test file called `{something}.test.js` in the
`resources/js` folder.

Here's an easyish one that uses Jquery, which many of my modules do. 

```js
/**
 * @jest-environment jsdom
 **/

const fields = require('./fields.js');

test('Test form is set and got',() =>{
	form  = document.createElement('form');
	fields.setForm(form);
	expect(fields.getForm()).toBe(form);
});

test('Adding a date button to an object',() =>{
	const question = {};
	fields.addDateControlButton(question);
	expect(typeof(question.$dateToNowBtn[0])).toBe('object');

});
```

Then run it with `npm run test`




