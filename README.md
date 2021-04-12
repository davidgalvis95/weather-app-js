##1. npm init
##2. npm install --save-dev webpack webpack-dev-server babel-core babel-loader babel-preset-env
#3. in package.json file in the scripts section set a new script as "build": "webpack"
#4. create a file for configuration as the one in webpack.config.js
#5. npm run build
#6. create an index html file that maps to the bundled file in this case <script src="./build/app.bundle.js"></script>
#7. add a start script to run the application in live mode, at development server in the scripts section of package.json
#8. npm install --save-dev babel-polyfill babel-preset-stage-0  to allow async await functions to be translated into ES5
#9. configure the webpack.config.js to support babel-polyfill in this case make entry.app to look like: 'app: ['babel-polyfill','./app/app.js']' and module.loaders.query.presets to look like:  presets: ['env', 'stage-0'], in order to enable the polyfill
#UPDATES!
#10 nowadays we should use in the webpack.config.js, module.rules.options.presets instead of module.loaders.query.presets and set the presets section as: presets: ['@babel/env'] replacing the old one
#11 npm install --save-dev @babel/core for the recent changes of this configuration
#12 npm install --save-dev @babel/preset-env also as 11
#in the package.json change the scripts.start script to look like "start": "webpack serve --output-public-path=/build/", thus replacing webpack-dev-server by webpack serve