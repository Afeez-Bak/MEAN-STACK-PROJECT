# MEAN-STACK-PROJECT

## Introduction

This is a documentation that explain the implementation, setup, configuration of MEAN stack project (book Management Web App) in AWS cloud. MEAN stack is one of the types of web stack that comprises of  MongoDB as the database for application data storage, ExpressJS as the Backend Application Framework, Angular as the frontend framework for user interface components and NodeJS as Javascript runtime Environment to run Javascript on a machine.

## PROJECT ARCHITECTURE


> AWS EC2 (Ubuntu 26.04) 
>    
> Backend Configuration
>
> Installing ExpressJS
> 
> Installing MongoDB
>
> MongoDB Database
>
> Testing backend Code without Frontend using RESTful API
>
> Frontend Creation
>
> Create React Componenets




# STEP 1 - PREREQUISITES
1. Login into AWS to create an Ec2 instance (LEMP SERVER) of t3.micro and Ubuntu Server 26.04 LTS (HVM), which was launched in eu-north 1b.

Ec2 Dashboard
![ec2 dashboard](<Images/1- Ec2 dashboard.png>)

```
ssh -i <sshkey.pem> Ubuntu@ipaddress
```
![ec2 login](<Images/2-ec2 login.png>)

2. Server update and upgrade
```
sudo apt update
sudo apt upgrade
```
![server update](<Images/3- update ec2 server.png>)
![server upgrade](<Images/4- server upgrade.png>)

3.  Add certificates

![certificate](<Images/5- add certificates.png>)
![certificate](<Images/5- add certificates2.png>)

4.  Install NodeJS

```
sudo apt install -y nodejs
```

![alt text](<Images/6- intall nodejs.png>)

# STEP 2 - MongoDB Installation
1.  Download the MongoDB public GPG key

![GPG Key1](<Images/7- mdb dep1.png>)
![GPG key2](<Images/8- mdb dep1.png>)

2.  Add MongoDB Repository

![mongodb repo](<Images/9- add mdb repo.png>)

3.  Install MongoDB

![Install MongoDB](<Images/10-intall mdb.png>)

4.  Start the server and verify that the database server is up ans running

![MGDB](<Images/11- mgdb not running.png>)

The command was not recognized because the command does not work for the updated version of MongoDB 5. the command was later changed to

```
sudo service mongod start
sudo systemctl status mongod
```

![MongoDB running](<Images/12- mgdb running.png>)

5.  Install Node Package Manager (NPM)

```
sudo apt install -y npm
```

![Npm](<Images/13-npm install.png>)

6.  Install Body-parser

```
sudo npm install body-parser
```

![body-parser](<Images/14- install body-parser.png>)

7.  Create 'Books' directory and initialize the npm

```
mkdir Books && cd Books
npm init
```

![Books](<Images/15- Book directory & npm init.png>)

8.  Create server.js file

```
vi server.js
```

![server.js](Images/16-server.js.png)


# STEP 3 - ExpressJS Installation

1.  Install Express and Mongoose package

```
sudo npm install express mongoose
```
![express](<Images/17- install express and mongoose.png>)

2.  Create 'apps' folder inside the previously created Books folder, then create routes.js file

```
mkdir apps && cd apps
vi routes.js
```
![apps folder](<Images/18a- apps folder.png>)

![routes.js](Images/18-routes.js.png)

3.  Create 'models' folder inside the previosly created apps folder, and then create book.js file

```
mkdir models && cd models
vi book.js
```

![model](<Images/19- model folder.png>)


![book](Images/20-book.js.png)


# STEP 4 - AngularJS
1.  create a 'public' folder and then create a script.js file

```
mkdir public && cd public
vi script.js
```

![public folder](<Images/21- publi folder.png>)

![script.js](<Images/22- script.js.png>)

2.  Create index.html file

![index.html](<Images/23-create index.html.png>)

![index.html](Images/24-index.html.png)

3.  start the server

```
node server.js
```

![syntax error](<Images/25- server.js syntax error.png>)

There was a syntax error when trying to start the server. There was an error within the code script for the routes.js file.

The code was corrected and the server was connected successfully

![routes.js](<Images/26- edit route.js code.png>)

![server running successfully](<Images/27-server.js running.png>)

4.   Open port 3300 in AWS web console

![port 3300](<Images/28- add port 3300 on ec2.png>)

5.  Accessing the server usinf the web browser

![...](<Images/29-web app.png>)

6.  Adding addition info to verify the server is functioning

![fie](<Images/30-books added.png>)

# Conclusion

