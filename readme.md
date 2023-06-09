# MERN

## Building -> Bundling  Minifiying

npm run build -> dist (vite), build (CRA)

* dist folder has compressed stuff which include:
  * CSS and images due to rollup
* dist folder is also gitignored (auto)
* dist folder only changes after `npm run build`

## Changes from Notes

Use `vite` rather than `CRA`

Change from `build` to `dist` folder
Remove `favicon`
use `node --watch server.js` to run Express
change `package.json` to `"type": "commonjs"`

In the future all Express routes should start with `/api`

## Dev

You need 2 running servers:

* Express -> `node --watch server.js`
* React -> `npm run dev`

or you `npm install concurrently --save-dev` and change `package.json`

```js
    "dev": "concurrently 'vite' 'node --watch server.js'",
```

## Proxy

Vite proxy info at <https://vitejs.dev/config/server-options.html#server-proxy>

```js
export default defineConfig({
  plugins: [react()],
  server: {
    proxy: {
      "/api": "http://localhost:3000"
    } 
  }
})
```

## Deployment

setup github repo and connect to cyclic
after you add .env -> add the variables to cyclic

### Add startup script

```json
  "scripts": {
    "start": "node server.js",
  }
```

## IMPORTANT

DO NOT SYNC UP THE CODE!!

## Clean up vite

main.jsx -> remove `index.css`
main.jsx -> fix import for App after the move

src, public -> belongs to React
every JS file outside -> belongs to Express 

## Project 3

* User journey
* Wireframe
  * url -> page? 
  * page -> components?
* Data model -> embedded / referencing 
  * Mock in google sheet
    * Each sheet is a Collection = User
    * Each col is a field -ID, Name etc
    * Each row is a document - SSS, Simon, etc