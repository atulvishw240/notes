
## Bundler

With **ES6** modules we learned how to split our application code across multiple `javascript` files. However, downloading a large number of files individually can reduce performance.

**Bundlers** are tools that let us write multiple files that are better for us to work with, then bundle them together into fewer smaller files which will ultimately be sent to the browser.

We provide the bundler with an **entry point**. It then builds a **dependency graph** from that file, combines all relevant files together, and then output a single file with all the necessary code included.

## Webpack

>Webpack is one of the most popular JavaScript bundlers.

## src and dist

When dealing with Webpack (or any other bundler or build tool), we have two very important directories: `src` (source) and `dist` (distribution).

`src` is where we keep all our source code. When we run Webpack to bundle our code, it will output the bundled files into the `dist` directory and this will be the directory we deploy from.

## Bundling JavaScript

In order to to bundle our `src` code into `dist` for deployment, we need to configure webpack. Create a `webpack.config.js` configuration file in the project root. This file will contain all the details related to bundling.

Below is a sample configuration file:
```js
// webpack.config.js
import path from "node:path";
import HtmlWebpackPlugin from "html-webpack-plugin";

export default {
  mode: "development",
  entry: "./src/index.js",
  output: {
    filename: "main.js",
    path: path.resolve(import.meta.dirname, "dist"),
    clean: true,
  },
  devtool: "eval-source-map",
  devServer: {
    watchFiles: ["./src/template.html"],
  },
  plugins: [
    new HtmlWebpackPlugin({
      template: "./src/template.html",
    }),
  ],
  module: {
    rules: [
      {
        test: /\.css$/i,
        use: ["style-loader", "css-loader"],
      },
      {
        test: /\.html$/i,
        use: ["html-loader"],
      },
      {
        test: /\.(png|svg|jpg|jpeg|gif)$/i,
        type: "asset/resource",
      },
    ],
  },
};
```

After configuration, for bundling your `src` code into `dist` run

`$ npx webpack`

from the command line from project root.

## Handling HTML

Since HTML isn't JavaScript, Webpack can't just bundle it straight away. So you need `HtmlWebpackPlugin` to bundle HTML. Install this with 

`$ npm install --save-dev html-webpack-plugin`

Now, we should create an HTML file for our project and set its path in `HtmlWebpackPlugin` inside of **plugins** array, like the configuration file above. **We do not need to put a script tag in this file!** `HtmlWebpackPlugin` will automatically add our output bundle as a script tag.

## Loading CSS



Most programming languages provide a way to import code from one file into another. JavaScript wasn’t originally designed with this feature, because JavaScript was designed to only run in the browser, with no access to the file system of the client’s computer (for security reasons). So for the longest time, organizing JavaScript code in multiple files required you to load each file with variables shared globally.

A JavaScript bundler is a tool that gets around the problem with a build step (which has access to the file system) to create a final output that is browser compatible (which doesn't need access to the file system).

## Webpack (Bundler)

We provide the bundler with an **entry point**. It then builds a **dependency graph** from that file, combines all relevant files together, and then outputs a single file with all the necessary code included.

### src and dist

`src` is where we keep all of our website's source code. `dist` is where we deploy from. 

## Bundling JavaScript

```js
// webpack.config.js
import path from "node:path"; // figures path by names (node.js)
import HtmlWebpackPlugin from "html-webpack-plugin";

export default {
  mode: "development",
  entry: "./src/index.js",
  output: {
    filename: "main.js",
    path: path.resolve(import.meta.dirname, "dist"),
    clean: true,
  },
};
```

With this, run webpack with `$ npx webpack` and you'll see that webpack created a `dist` directory for us containing a `main.js` file! 

### Handling HTML

Since HTMl isn't JavaScript, webpack can't just bundle it straight away.
`$ npm install --save-dev html-webpack-plugin`

```js
// webpack.config.js
import path from "node:path";
import HtmlWebpackPlugin from "html-webpack-plugin";

export default {
  mode: "development",
  entry: "./src/index.js",
  output: {
    filename: "main.js",
    path: path.resolve(import.meta.dirname, "dist"),
    clean: true,
  },
  plugins: [
    new HtmlWebpackPlugin({
      template: "./src/template.html",
    }),
  ],
};
```

All we’re doing here is making sure our Webpack configuration has access to HtmlWebpackPlugin, then adding it as a plugin to the configuration object. Inside the HtmlWebpackPlugin constructor call, we pass in any options. For now, we’re only interested in the `template` option.

### Loading CSS

`$ npm install --save-dev style-loader css-loader`

