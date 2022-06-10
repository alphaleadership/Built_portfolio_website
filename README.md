# Built_portfolio_website

Comment créer un site web de portfolio en utilisant Next.js, Chakra UI, Framer Motion et Three.js

# Ingredients

| Ingredients   | Usage                                                                                 |
| ------------- | ------------------------------------------------------------------------------------- |
| React         | A JavaScript library for building UIs                                                 |
| Next.js       | A React framework with hybrid static & server rendering, and route pre-fetching, etc. |
| Chakra UI     | A simple, modular and accessible component library for React                          |
| Framer Motion | An animation library for React                                                        |
| Three.js      | 3D library for JavaScript                                                             |

# Project Structure

> Very similar to the structure of a monorepo
> The other folders are not mandatory, and contain additional files (resources, about, etc ...)

```cmd
$PROJECT_ROOT
# Page files
	pages
# React conponent files
	lib
# Static files for imahes and 3d model file
	public
```

# Links
[Accéder à la vidéo](https://youtu.be/bSMZgXzC9AA)

# Product
## 1. Create a new project & configure this project

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

And create a ```prettier.config.js``` with these lines :

