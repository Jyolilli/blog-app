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

npm install --save body-parser

```
{
    "presets": ["@babel/preset-env"]
}
```

run the express server with:

```
npx babel-node src/server.js
```

## To automatically update server

```
npm install --save-dev nodemon
```

then run the express server with:

```
npx nodemon --exec npx babel-node src/server.js
```

## Database

Major problems with setting up database directory
because of the instructions
sudo mkdir -p /data/db
didn't work because mac os is now Read-only file system

---

Mongo Instructions
https://github.com/mongodb/homebrew-brew

Fortunately, the team of mongodb is maintaining a custom Homebrew tap. You can uninstall the old mongodb and reinstall the new one from the new tap.
If already installed:
brew services stop mongodb
brew uninstall mongodb

```
brew tap mongodb/brew
brew install mongodb-community
brew services start mongodb-community
```

```
a configuration file: /usr/local/etc/mongod.conf
a log directory path: /usr/local/var/log/mongodb
a data directory path: /usr/local/var/mongodb
```

to open the shell:

```
mongo
```

create a collection:

```
use jyolilli-blog
```

enter data:

```
db.articles.insert([{
name: 'learn-react',
upvotes: 0,
comments: [],
}, {
name: 'learn-node',
upvotes: 0,
comments: [],
}, {
name: 'my-thoughts-on-resumes',
upvotes: 0,
comments: [],
}])
```

To have a look at our collections:

```
db.articles.find({})
```

or

```
db.articles.find({}).pretty()
```

or find something in particular:

```
db.articles.find({ name: 'learn-react' }).pretty()
```

or find one thing in particular:

```
db.articles.findOne({ name: 'learn-react' })
```

To exit mongo shell:

```
Ctrl + c
```

## Back to the Express Server (Backend Directory)

Install mongo allow us to connect to and modify our database from our express server
to persist data

```
npm install --save mongodb
```

# To run the server

Make sure db is running

```
brew services start mongodb-community
```

Start the server

```
npm start
```
