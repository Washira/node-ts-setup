## Installation

Create file for entrypoint of project `server.ts`

Implement some code

```
console.log('test')
```

Run server.ts

```
node server.ts
```

It will be fine until you implement ts code like this

```
const test: number = 0
```


Global installation

```
yarn global add tsc typescript ts-node ts-node-dev
```

You can run ts file like it

```
tsc server.ts
```

It will be converted to a file of Javascript by generate new file (in this case is `server.js`)

Then you can run directly on .js file as `node server.js`.

### What is `ts-node` and `ts-node-dev`?

`ts-node` is used to compile .ts with tsc and run .js with `node`.

It works like `ts-node server.ts` equals to `tsc && node server.js`

And `ts-node-dev`, it works like `nodemon` for TypeScript.

## TypeScript Configuration

You can config ts by init commands

```
tsc --init
```

see `tsconfig.fson` will be display, uncomment `rootDir` to specify the root folder within your source files.

After that, you can set up the root folder for compiler by change `"./"` to be any directory you need.

In this case, we move `server.ts` into `src`, and set up `rootDir` to be `"./src"`.

Anything outside `src` would not be compiled.

### A folder for contain .js after compile from .ts

We define a new row on `tsconfig.fson` if below `rootDir` will be better.

Named `outDir` for contain .js file from compile .ts, in this case, call it to `dist`.

Then, see `allowJs` and uncomment it, using to allow .js files to be a part of your program.

And the project will be allowed to compile .js files as well as .ts file.

## Add Libraries

Generate `package.json` for the project as normal.

```
npm init --y
```

Add `.gitignore` file for control unnecessary files or folders to the version control.

```
touch .gitignore
```

inside the file, type `node_modules` to ingore the folder pushed to Git.

Then, add Express

```
yarn add express
```

Add 

```
yarn add @types/express -D

or

yarn add @types/express --dev
```

## Add Alias on `package.json`

In `script` add new line to be

```
 "start": "ts-node src/server.ts"
```
Using when you need start server, you just type command `yarn start` instead of `ts-node src/server.ts`.