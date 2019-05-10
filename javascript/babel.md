## [@babel/polyfill][1]

>  Intended to be used in an application rather than a library/tool. 

 - Is Polyfill, and need to run before your code, so need it to be a dependency, not a devDependency
 - Use with [@babel/preset-env][2] with `useBuiltIns` option

There are several ways to use this lib..

 * `useBuiltIns: 'usage'` specified in `.babelrc` and do not include @babel/polyfill
 * `useBuiltIns: 'entry'` specified in `.babelrc` then include @babel/polyfill on to of main file
 * `useBuiltIns: false` specified in `.babelrc` then add @babel/polyfill directly to the entry array in your webpack.config.js.

## [@babel/preset-env][2]

> Allows you to use the latest JavaScript without needing to micromanage which syntax transforms 
> Takes any target environments you've specified and checks them against its mappings to compile a list of plugins and passes it to Babel.

 - Note that @babel/preset-env does not support stage-x plugins.
 - Recomended to use `.browserslistrc` to specify your environment
 - By default will use browserslist config sources unless either the targets or ignoreBrowserslistConfig options are set.

The option `useBuiltIns` has

 * `usage`: Adds direct references to the core-js module on file that needed it
 * `entry`: Replace `import "@babel/polyfill"` by all `core-js` imnports needed for the entire app;
 * `false`: Don't add polyfills automatically per file, you will need `import "@babel/polyfill"` with all polyfills


[1]: https://babeljs.io/docs/en/babel-polyfill
[2]: https://babeljs.io/docs/en/babel-preset-env
[3]: https://github.com/browserslist/browserslist
