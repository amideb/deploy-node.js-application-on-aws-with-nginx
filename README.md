# Deploy a Full Stack Node.js & React Application on AWS with Nginx 

##Requirements

- Ubuntu Server - ex. Putty
- AWS pem key
- Node.js application
- React.js application

## Setup putty with AWS key
- https://asf.alaska.edu/how-to/data-recipes/connect-to-your-ec2-instance-using-putty-v1-1/

## Setup Ubuntu Server

- We will be installing all the dependencies on our EC2 instance needed for our app to run. To install node, run these commands in your terminal.

 ```sh
nvm install 8.12
node -v
``` 

- Install pm2 to run your app in the background.
```sh
sudo npm install pm2 -g
sudo apt-get update
``` 
- How to check anything is running on your server
```sh
pm2 list
``` 
- Delete/Stop running app from server
```sh
pm2 delete appname
``` 

## Run Node.js Application

- push your code on github
- git clone the repo on your ubuntu server with "git clone"
- go inside the project folder
```sh
npm i
```
-start the node.js server with pm2 
```sh
pm2 start app.js
```
- Enjoy!


## Run React.js Application

- Go inside your react app's package.json and add a port inside the start script
```sh
"scripts": {
    "start": "PORT=3008 react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject"
  },
```
- Now push your code on github
- Clone it on server
- Go inside the application root folder
 ```sh
npm i
npm run build


```
