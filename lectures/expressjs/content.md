# Express.js

-
-
## Lecture Overview
* Express is a Node.js web application framework

-
-
### Hello Express

-
#### Express App Setup

* Create an npm project: `npm init -y`
* Install Express: `npm install express --save`
* Install Nodemon: `npm install -g nodemon`
* Set `main` in `package.json` to `app.js` 
* Create a `app.js` file

-
#### Express Hello World
```javascript
const express = require('express');
const app = express();
app.listen(3000);
```

-
-
### Basic Routing

-
#### Get
```javascript
app.get('/', (request, response) => {
    response.send('Hola Mundo!');
});

app.get('/english', (request, response) => {
    response.send('Hello World!');
});

app.get('/lame', (request, response) => {
    response.send('Hello Code Rhino!');
});
```

-
#### Post
```javascript
const express = require('express');
const bodyParser = require('body-parser');

const app = express();

app.use(bodyParser.urlencoded({ extended: false}));
app.use(bodyParser.json());

app.post('/howdy', (req, res) => {
  res.send(`Howdy ${req.body.name}`);
});

app.listen(3000, () => {
    console.log('The application is running on localhost:3000!')
});
```

-
#### Rerouting
```javascript
app.post('/cool', (req, res) => {
  console.log('Goodbye Code Rhino!');
  res.redirect('/');
});
```

-
-
### Request Data

-
#### Route Parameters
```javascript
router.get('/:id', (req, res) => {
    res.send(req.params.id)
});
```
A colon signifies a path parameter. This can be thought of as a variable in our route. Whatever value the user sends in the route can be accessed through the request paramerters. For example, if the url was `localhost:8080/3` than id would be 3

-
#### Route Queries
URL: `https:codediff.com/classes?lang=js`

```javascript
app.get("/classes", (req, res) => {
    console.log(req.query) //{ language: 'js' }
})
```

-
#### Cookies
![cookie monster](https://media.giphy.com/media/bAlYQOugzX9sY/giphy.gif)


```javascript
//Cookie Parser Middleware
app.use(cookieParser());

//Create a cookie
res.cookie('username', req.body.username);

// Get all cookies
let cookies = req.cookies;

// Clear a cookie
res.clearCookie('cookiename');
```

-
-
### Misc.

-
#### Static Files 
```javascript
app.use('/static', express.static('public'));
```

-
#### Modular Routes
```javascript
//MainRoutes.js
const express = require('express');
const router = express.Router();

router.get('/', (req, res) => {
    const name = req.cookies.username;
    if (name) {
      res.render('index', { name });
    } else {
      res.redirect('/hello');
    }
});

module.exports = router;
```

```javascript
//app.js
const app = express();
const mainRoutes = require('./routes/MainRoutes');
app.use('/main', mainRoutes);
app.listen(3000);
```

-
#### Mock Data

```javascript
//students.json
["Kaleb", "Tariq", "Stephanie"]
```
```javascript
const { data } = require('./students.json');
const { students } = data;
router.get('/students', (req, res) => {
    res.send(students);
});
``` 

-
### Middleware

Middleware takes in the `request` and `response`, preforms an action, and goes onto the `next` middleware. This happens on each request

```javascript
app.use((req, res, next) => { 
    console.log("Hello Middleware");
    next();
});
```

![diagram](https://res.cloudinary.com/practicaldev/image/fetch/s--BooDKgDv--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/babo58difyn1wkvyg8zv.png)
