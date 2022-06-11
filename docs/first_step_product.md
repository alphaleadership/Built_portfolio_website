# 1. Create a new project & configure this project

First, let's create a folder and then install the necessary libraries.
```shell
~$ mkdir portfolio
~$ cd portfolio
~\portfolio $ npm init -y
~\portfolio $ npm i @chakra-ui/react @emotion/react @emotion/styled framer-motion next react react-dom
~\portfolio $ npm i -D eslint eslint-config-next prettier
```
Next, let's modify the ``package.json`` file to add scripts, like this:
```json
"scripts": {
    "dev": "next dev -H 0.0.0.0",
    "build": "next build",
    "prettier" : "prettier -write .",
    "lint": "next lint"
  },
 ```
This will make using the commands much easier.

Let's continue the configuration.
Add a ```.eslintrc.json``` file with these lines : 
```json
{
    "root": true,
    "extends": "next",
    "rules": {
        "no-unused-vars": [
            "error",
            {
                "argsIgnorePattern": "^_",
                "varsIngnorePattern": "^_"
            }
        ]
    }
}
```
Let's move on to the prettier configuration.
First, create a ```prettier.config.js``` with these lines :
```js
const options = {
    arrowParens: 'avoid',
    singleQuote: true,
    bracketSpacing: true, 
    endOfLine: "lf",
    semi: false,  
    tabWidth: 2,
    trailingComma: 'none'
}

module.exports = options
```

And add the ```.prettierignore``` file : 
```js
node_modules
.next
```

Let's go to the configuration of Next with the file ```next.config.js```
```js
module.exports = {
    reactStrictMode: true
}
```

So here's what your architecture should roughly look like right now : 
[structure1](./image/structure1.png)
> Note: The ```doc``` folder, ```LICENSE``` and ```.md``` files are added by me and are not necessary.

In the second stage of production, we will:
1. Create the index page
2. Integrate with Chakra UI