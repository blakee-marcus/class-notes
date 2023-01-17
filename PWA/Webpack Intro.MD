# Webpack Intro

Webpack is a JavaScript module bundler that takes your JavaScript code and its dependencies and generates a single bundle file that can be included in your HTML file. To get started with Webpack, you'll need to have Node.js and npm (Node Package Manager) installed on your computer.

1. Create a new project directory and navigate to it in the command line.
2. Initialize a new npm project by running `npm init -y` to create a package.json file.
3. Install webpack and webpack-cli as a development dependency by running `npm install webpack webpack-cli --save-dev`
4. Create a new file in your project directory called webpack.config.js. This file will contain the configuration for your webpack build.
5. In the webpack.config.js file, define your entry point and output path:

```javascript
module.exports = {
  entry: './src/index.js',
  output: {
    path: __dirname + '/dist',
    filename: 'bundle.js',
  },
};
```

6. Create a new directory called "src" in your project directory and add an index.js file to it. This will be the starting point for your application.
7. In the command line, run `npx webpack` to build your application. This will create a new "dist" directory with the bundle.js file.
8. Add the bundle.js file to your HTML file.
9. If you want to use webpack in development mode, you can run `npx webpack --watch` and webpack will watch for changes in your files and rebuild the bundle automatically.

You can customize and add more features as you need, this is just a basic starting point.
