
>webpack is one of the most popular javascript bundler
## Bundling

>[!question] What's the job of a bundler?

We provide the bundler (**webpack**) with an entry point. It then builds a dependency graph from that file, combines all relevant files together, and then outputs a single file with all the necessary code included.

## Webpack

1. Create a `package.json` file with `$ npm init -y --init-type=module`
2. Install webpack with `$ npm install --save-dev webpack webpack-cli webpack-dev-server`

Installing webpack will create `node_modules` directory and which contains the webpack's actual code. 

## src and dist

When dealing with any bundler or build tool, we have two directories. `src` for source and `dist` for distribution.

When we run webpack to bundle our code, it will output the bundled files into the `dist` directory. Similarly, to deploy our website we only need `dist` code and nothing else.

To bundle webpack, use command `$ npx webpack`.  Since HTML and CSS aren't JavaScript it requires plugin to bundle them correctly.


