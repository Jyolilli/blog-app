# blog-backend

cd backend
npm init -y
npm install --save express
mkdir src
cd src
touch server.js
npm install --save-dev @babel/core @babel/node @babel/preset-env
cd backend

touch .babelrc

```{
    "presets": ["@babel/preset-env"]
}
```

run the express server with:

```
npx babel-node src/server.js
```
