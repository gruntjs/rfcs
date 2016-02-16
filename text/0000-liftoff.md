- Feature Name: liftoff
- Start Date: 2016-02-15
- RFC PR: (leave this empty)
- Grunt Issue: (leave this empty)

# Summary
[summary]: #summary

Implement [Liftoff](https://github.com/js-cli/js-liftoff) for the CLI so
Gruntfiles can be written in the language of the user's choice without needing
to register each of them directly into Grunt.

# Motivation
[motivation]: #motivation

* Let users define their Gruntfile in a language or their choice.
* Let users specify v8 flags.
* Removes dependencies (`coffee-script`) and code from core Grunt.

# Detailed design
[design]: #detailed-design

Replace the CLI with:

```js
var Liftoff = require('liftoff');
var v8flags = require('v8flags');
var argv = require('minimist')(process.argv.slice(2));

v8flags(function (err, v8flags) {
  var Grunt = new Liftoff({
    name: 'grunt',
    // Support a number of languages based on file extension
    extensions: require('interpret').jsVariants,
    // Flags that are v8 flags will be loaded into node instead of Gruntfile
    v8flags: v8flags
  });

  Grunt.launch({
    cwd: argv.cwd,
    configPath: argv.gruntfile,
    require: argv.require,
    completion: argv.completion,
    verbose: argv.verbose
  }, function (env) {
    // Load Gruntfile
  });
});
```

This will support Gruntfiles in a number of languages, including CoffeeScript,
Babel, TypeScript, LiveScript, JSX and many more: https://github.com/js-cli/js-interpret/blob/master/index.js#L96

If a language is not natively supported a user can do:

```shell
npm install custom-lang
grunt --require custom-lang/register
```

# Drawbacks
[drawbacks]: #drawbacks

* None known.

# Alternatives
[alternatives]: #alternatives

* None known.

# Unresolved questions
[unresolved]: #unresolved-questions

* In doing this, which parts are not backwards compatible?
