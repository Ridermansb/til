# BrowsersList

> The config to share target browsers and Node.js versions between different front-end tools.

## Usage

Just create `.browserslistrc` file with 

```
# Browsers that we support

last 1 version
> 1%
maintained node versions
not dead
```

Then other tools like babel or AutoPrefixer will use this list.

Browserslist will use [Can I Use][2] data for this queries.

## Tips

 - `npx browserslist` to list all supported browser for current query
 - `browserslist --coverage=US "> 1% in US"` to list how mutch users are cover by your config
 - Use [`browserslist-useragent-regexp`][3] to test if current browser has support by current config

## Shareable Configs

It's possible to create npm package with browserslist config and share with others, just create npm package with ``browserslist-config-` prefix or with scoped like `@scope/browserslist-config-mycompany`

```
  "browserslist": [
    "extends browserslist-config-mycompany"
  ]
```

Just export an array with queries `browserslist-config-mycompany/index.js`

```
module.exports = [
  'last 1 version',
  '> 1%',
  'ie 10'
]
```

## Environments

On your config file, you can specify custom queries for environment

```
[production staging]
> 1%
ie 10

[development]
last 1 chrome version
last 1 firefox version
```

Just remamber to set `BROWSERSLIST_ENV` or `NODE_ENV`

[1]: https://github.com/browserslist/browserslist
[2]: https://caniuse.com/
[3]: https://github.com/browserslist/browserslist-useragent-regexp
