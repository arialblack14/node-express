# Exercise (Instructions): Introduction to Express Part 1

In this exercise, you will make use of the Express framework to implement similar functionality as implemented by the HTTP module based servers in the previous exercise. At the end of this exercise, you will be able to:

Implement a simple web server using Express framework
Implement a web server that serves static content
A Simple Server using Express

Create a folder named node-express at a convenient location on your computer and move to that folder.
Copy the public folder from node-http to this folder.
Create a file named `server-1.js` and add the following code to it:

```
var express = require('express'),
     http = require('http');

var hostname = 'localhost';
var port = 3000;

var app = express();

app.use(function (req, res, next) {
  console.log(req.headers);
    res.writeHead(200, { 'Content-Type': 'text/html' });
  res.end('<html><body><h1>Hello World</h1></body></html>');

});

var server = http.createServer(app);

server.listen(port, hostname, function(){
  console.log(`Server running at http://${hostname}:${port}/`);
});
```
Then, install the Express framework in the folder by typing the following at the prompt:
     `npm install express --save`
Start the server by typing the following at the prompt, and then interact with the server:
     `node server-1`
Serving Static Files

Create a file named `server-2.js` and add the following code to it:
```
var express = require('express');
var morgan = require('morgan');

var hostname = 'localhost';
var port = 3000;

var app = express();

app.use(morgan('dev'));

app.use(express.static(__dirname + '/public'));

app.listen(port, hostname, function(){
  console.log(`Server running at http://${hostname}:${port}/`);
});
```
Then, install morgan by typing the following at the prompt:

     `npm install morgan --save`

Start the server and interact with it and observe the behavior.
Conclusions

In this exercise you learnt to use the Express framework to design and implement a web server.
