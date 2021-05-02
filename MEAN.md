# MEAN Stack Deployment Using Ubuntu

# Install NodeJs

Upgrade & Update Ubuntu

![image](https://user-images.githubusercontent.com/49937302/115993121-ef9ba600-a603-11eb-9a6f-13e1e12c623c.png)

Install node JS

![image](https://user-images.githubusercontent.com/49937302/115993186-443f2100-a604-11eb-9a50-5a288e330759.png)

# Install MongoDB

Setup and install mongdoDB

![image](https://user-images.githubusercontent.com/49937302/115993238-82d4db80-a604-11eb-8b55-38c85a7c8499.png)

![image](https://user-images.githubusercontent.com/49937302/115993244-8700f900-a604-11eb-9000-d3900dc31878.png)

![image](https://user-images.githubusercontent.com/49937302/115993248-89fbe980-a604-11eb-81c0-f4776352449e.png)

start and verify mongodb service started successfully

![image](https://user-images.githubusercontent.com/49937302/115993322-d9dab080-a604-11eb-8361-de4434c69122.png)

Install NPM (node package manager)

![image](https://user-images.githubusercontent.com/49937302/115993352-f676e880-a604-11eb-919d-b97e7685d27b.png)

Install 'body-parser' package, used to process JSON files passed requests to server

![image](https://user-images.githubusercontent.com/49937302/115993386-1d351f00-a605-11eb-803f-5eb6da5ef5c0.png)

create directory books and initialize npm

![image](https://user-images.githubusercontent.com/49937302/115993421-42299200-a605-11eb-82e6-c4f16a437f82.png)

Create server.js file and paste the below code

var express = require('express');
var bodyParser = require('body-parser');
var app = express();
app.use(express.static(__dirname + '/public'));
app.use(bodyParser.json());
require('./apps/routes')(app);
app.set('port', 3300);
app.listen(app.get('port'), function() {
    console.log('Server up: http://localhost:' + app.get('port'));
});

![image](https://user-images.githubusercontent.com/49937302/115993452-64bbab00-a605-11eb-8cbc-0d9ee0325493.png)


# Install express and setup route to servers

![image](https://user-images.githubusercontent.com/49937302/115993465-71400380-a605-11eb-87bf-1ba17bb030f2.png)

Create directory apps & create routes.js under apps directory

![image](https://user-images.githubusercontent.com/49937302/115993513-af3d2780-a605-11eb-87d7-c3931f495deb.png)

create models directory and create book.js under models directory

![image](https://user-images.githubusercontent.com/49937302/115993541-e4e21080-a605-11eb-82a0-de282193b08e.png)

# Access the routes with angularJS

create public directory and add file script.js

![image](https://user-images.githubusercontent.com/49937302/115993650-44402080-a606-11eb-830f-9b1c24c6af71.png)

create index.html under public directory

![image](https://user-images.githubusercontent.com/49937302/115993656-54f09680-a606-11eb-94f2-1553a9ee0a97.png)

navigate back to books directory & start the server

![image](https://user-images.githubusercontent.com/49937302/115993694-823d4480-a606-11eb-949d-f2f770bae641.png)

verify the html returns succeesfully using curl -s http://localhost:3300

![image](https://user-images.githubusercontent.com/49937302/115993711-9d0fb900-a606-11eb-9cc4-feaa2a0b7f78.png)

allow port 3300 on security group inbound rule that is attached to the ubuntu server

![image](https://user-images.githubusercontent.com/49937302/115993761-d5af9280-a606-11eb-87d9-d2d83fa893ce.png)

Verify on the browser and browse to your public ip of the ubuntu server
it should return webpage successfully

![image](https://user-images.githubusercontent.com/49937302/115993793-f677e800-a606-11eb-9d7e-294143f434a1.png)
