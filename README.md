# `au-default-2`

This project is bootstrapped by [aurelia-cli](https://github.com/aurelia/cli).

For more information, go to https://aurelia.io/docs/cli/webpack

## Run dev app

Run `npm start`, then open `http://localhost:8080`

You can change the standard webpack configurations from CLI easily with something like this: `npm start -- --open --port 8888`. However, it is better to change the respective npm scripts or `webpack.config.js` with these options, as per your need.

To enable Webpack Bundle Analyzer, do `npm run analyze` (production build).

To enable hot module reload, do `npm start -- --hmr`.

To change dev server port, do `npm start -- --port 8888`.

To change dev server host, do `npm start -- --host 127.0.0.1`

**PS:** You could mix all the flags as well, `npm start -- --host 127.0.0.1 --port 7070 --open --hmr`

For long time aurelia-cli user, you can still use `au run` with those arguments like `au run --env prod --open --hmr`. But `au run` now simply executes `npm start` command.

## Build for production

Run `npm run build`, or the old way `au build --env prod`.

## Unit tests

Run `au test` (or `au jest`).

To run in watch mode, `au test --watch` or `au jest --watch`.


# Convert to use SnowPack

```
mkdir public 
mv index.ejs public/index.html
mv statix/favicon.ico public
cp SNOWPACK_EXAMPLE/snowpack.config.js .
cp -r SNOWPACK_EXAMPLE/plugin .
```

In **package.json**

replace the scripts section with:
```json
"scripts": {
    "start": "snowpack dev",
    "build": "snowpack build"
  },
```

add these dependencies to "devDependencies":
```
    "aurelia-plugin": "file:plugin",
    "@snowpack/plugin-dotenv": "^2.0.5",
    "@snowpack/plugin-typescript": "^1.2.0",
    "@types/snowpack-env": "^2.3.2",
    "snowpack": "^3.2.2",
```

then rerun: ```npm install```

npm i --save @aurelia/runtime-html

remove from package.json all dependencies having in any part of the name:
- webpack
- babel
- jest

remove the "jest" section from package.json

remove the node_modules directory,
and rerun ```npm install```
