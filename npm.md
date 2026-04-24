
>`npm` does not stand for "Node Package Manager". It helps in **dependency management**.

As applications get more complex, it gets hard to manage dependencies. `npm` helps us manage these dependencies through `package.json`.

## package.json

- lists the packages your project depends on
- specifies versions of a package that your project can use using **semantic versioning rules**
- makes your build reproducible, and therefore easier to share with other developers


## Create a new `package.json` file

- run `npm init` command from the root directory of your project
- to create a default `package.json` file run - `npm init --yes or -y`
- You can customize `package.json` questionnaire if you're creating a lot of `package.json` files and want all of them to look same
- You can set defaults like name, email, and other details for every `package.json` file you create

>`node.js` is a JavaScript runtime designed to run on the server.


---

## A Little bit of History

To use JavaScript we do:
```js
<script src="index.js"></script>
```

In earlier days (early 2000s) if you wanted to use a 3rd party library in your application. You'll perform these steps:
- download the library
- link it in your html file

```js
<script src="moment.min.js"></script> // Moment library
<script src="index.js"></script>
```

Suppose if moment library author updates the library and you want this new version. Then, you'll have to manually download this updated library code and then link it again. You'll have to do this each time you want an updated version of library.

### Here comes the package manager

`npm` was originally a package manager made specifically for `node.js`.  Now to install moment library you would run:
`$ npm install moment --save`

The above command does two things:
- Download `moment.js` package into a folder called **node_modules**
- Automatically updates **package.json** file to keep track of `moment.js` as a project dependency

So no longer have to manually download `moment.js` from the website, we can automatically download and update it using `npm`. When sharing project you don't have to share **node_modules** folder, people can run `$ npm install` to install all the dependencies.

```js
<script src="node_modules/moment/min/moment.min.js"></script>
```

So the good thing is that we can now use npm to download and update our packages through the command line. The bad thing is right now we’re digging through the **`node_modules`** folder to find the location of each package and manually including it in our HTML. That’s pretty inconvenient, so next we’ll take a look at how to automate that process as well.

### Using a JavaScript module bundler (webpack)

Your browser doesn't have access to the file system (security reasons), that's why JavaScript wasn't designed to support `import/export` statements like other programming Languages like Java, Python, etc. 

Your browser doesn't have access to the file system but we want to use file system (`import/export`) to avoid global scope problem. This is where bundler comes in, it introduces an intermediate step called **build**.

It replaces all `import/export` statements with their respective code, so now we only have a single javascript file without any `import/export` statements, which our browser understands.


