A check to ensure that the node.js buildpack provides a working node
environment for subsequent buildpacks.

When used in a .buildpacks file with multi-buildpack,
output should be something like this:

```term
$ git push heroku master

[master b4a1d45] empty
Counting objects: 1, done.
Writing objects: 100% (1/1), 186 bytes | 0 bytes/s, done.
Total 1 (delta 0), reused 0 (delta 0)
remote: Compressing source files... done.
remote: Building source:
remote:
remote: -----> Fetching custom git buildpack... done
remote: -----> Multipack app detected
remote: =====> Downloading Buildpack: https://github.com/heroku/heroku-buildpack-nodejs
remote: =====> Detected Framework: Node.js
remote:
remote: -----> Reading application state
remote:        package.json...
remote:        build directory...
remote:        cache directory...
remote:        environment variables...
remote:
remote:        Node engine:         0.10.38
remote:        Npm engine:          unspecified
remote:        Start mechanism:     npm start
remote:        node_modules source: package.json
remote:        node_modules cached: true
remote:
remote:        NPM_CONFIG_PRODUCTION=true
remote:        NODE_MODULES_CACHE=true
remote:
remote: -----> Installing binaries
remote:        Downloading and installing node 0.10.38...
remote:        Using default npm version: 1.4.28
remote:
remote: -----> Building dependencies
remote:        Restoring node modules from cache
remote:        Pruning unused dependencies
remote:        valid
remote:        Installing node modules
remote:
remote: -----> Checking startup method
remote:        No Procfile; Adding 'web: npm start' to new Procfile
remote:
remote: -----> Finalizing build
remote:        Creating runtime environment
remote:        Exporting binary paths
remote:        Cleaning npm artifacts
remote:        Cleaning previous cache
remote:        Caching results for future builds
remote:
remote: -----> Build succeeded!
remote:
remote:        express@0.0.0 /tmp/build_6a46f72ec9eec84c800960e8d996cf91
remote:        ├── body-parser@1.12.4
remote:        ├── cookie-parser@1.3.4
remote:        ├── debug@2.1.3
remote:        ├── express@4.12.3
remote:        ├── jade@1.9.2
remote:        ├── morgan@1.5.3
remote:        └── serve-favicon@2.2.0
remote:
remote: =====> Downloading Buildpack: https://github.com/hunterloftis/buildpack-node-env
remote: =====> Detected Framework: Node.js Environment Check
remote: Checking available Node.js environment...
remote:
remote: Build dir: /tmp/build_6a46f72ec9eec84c800960e8d996cf91
remote: Cache dir: /app/tmp/cache
remote: Env dir: /tmp/d20150512-131-fryum5
remote:
remote: Node version: v0.10.38
remote: Node location: /tmp/build_6a46f72ec9eec84c800960e8d996cf91/.heroku/node/bin/node
remote:
remote: Npm version: 1.4.28
remote: Npm location: /tmp/build_6a46f72ec9eec84c800960e8d996cf91/.heroku/node/bin/npm
remote:
remote: NODE_HOME: /tmp/build_6a46f72ec9eec84c800960e8d996cf91/.heroku/node
remote: WEB_CONCURRENCY:
remote: PATH: /tmp/build_6a46f72ec9eec84c800960e8d996cf91/.heroku/node/bin:/tmp/build_6a46f72ec9eec84c800960e8d996cf91/node_modules/.bin:/app/bin:/app/vendor/bundle/bin:/app/vendor/bundle/ruby/2.2.0/bin:vendor/bundle/ruby/1.9.1/bin:/usr/local/bin:/usr/bin:/bin:bin:/tmp/codon/vendor/bin
remote:
remote: Using release configuration from last framework (Node.js Environment Check).
remote: -----> Discovering process types
remote:        Procfile declares types -> web
remote:
remote: -----> Compressing... done, 6.7MB
remote: -----> Launching... done, v9
```
