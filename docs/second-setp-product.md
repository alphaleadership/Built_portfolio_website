# 2. Create index page & integrate Chrakra UI

In this product step, we will : 
1. Create index page 
2. Integrate Chackra UI 

Let's modify the project architecture with this command:
```cmd
\portfolio $ mkdir pages && mkdir components && mkdir components/layouts
\portfolio $ cd pages && touch index.js
\portfolio\ $ cd ../
```
Note: On Windows, you will have to create the file manually.
Let's quickly modify the index.js file and test if everything we've done so far works.
```js
const Page = () => {
    return (
        <div>Hello</div>
    )
};

export default Page;
```

Let's test if everything works with the following command:
```
\portfolio $ npm run dev
```
Go to the localhost on port 3000 ( localhost:3000 ). If it works, you'll have a page that loads with just one word, "Hello".

Let's create a ```main.js``` file in the ```./components/layouts``` folder and modify it. 
```js
import Head from 'next/head';
import { Box, Container } from '@chackra-ui/react';

const Main = ({ children, router }) => {
    return (
        <Box as="Main" pb={8}>
            <Head>
                <meta name="viewport" content="width=device-width, initial-scale=1"/>
                <title>Portfolio Example by WolfyzDev</title> 
            </Head>

            <Container maxW="container.md" pt={14}>
                { children }
            </Container>
        </Box>
    );
};

export default Main;
```
## Integrete Chackra UI 
Let's start the next step: integrate Chakra UI
In a folder ```pages```, create a ```_app.js``` file and modify it : 
```js
import { ChakraProvider } from "@chakra-ui/react";
import Layout from "../components/layouts/main";

const website = ( { Component, pageProps, router } ) => {
    return (
        <ChakraProvider>
            <Layout router = { router }>
                <Component {...pageProps} key = {router.route} />
            </Layout>
        </ChakraProvider>
    );
};

export default website;
```
Relaunch the dev command and go to the localhost (same access address as earlier).
```
\portfolio $ npm run dev
```
Here is the result we should have if everything works:

______
Minuter : 9-05
Result : Pb with bk-color (#fff <> black) but :check: font :check: padding