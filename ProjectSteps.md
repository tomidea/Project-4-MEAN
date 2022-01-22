# MEAN STACK DEPLOYMENT TO UBUNTU IN AWS
MEAN Stack is a combination of following components:
1. MongoDB (Document database) – Stores and allows to retrieve data.
2. Express (Back-end application framework) – Makes requests to Database for Reads and Writes.
3. Angular (Front-end application framework) – Handles Client and Server Requests
4. Node.js (JavaScript runtime environment) – Accepts requests and displays results to end user


## Step 1: Install NodeJs
Update ubuntu
*sudo apt update*
img

Upgrade ubuntu
*sudo apt upgrade*
img

Add certificates
*sudo apt -y install curl dirmngr apt-transport-https lsb-release ca-certificates*
img
*curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -*
img

Install NodeJS
*sudo apt install -y nodejs*
img

## Step 2: Install MongoDB
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 0C49F3730359A14518585931BC711F9BA15703C6

echo "deb [ arch=amd64 ] https://repo.mongodb.org/apt/ubuntu trusty/mongodb-org/3.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.4.list
img

Install MongoDB
*sudo apt install -y mongodb*
img

Start The server
*sudo service mongodb start*

Verify that the service is up and running
*sudo systemctl status mongodb*
img

Install npm – Node package manager.
*sudo apt install -y npm*
img

Install body-parser package
We need ‘body-parser’ package to help us process JSON files passed in requests to the server.
*sudo npm install body-parser*
img

Create a folder named ‘Books’
*mkdir Books && cd Books*

In the Books directory, Initialize npm project
*npm init*
img
Add a file to it named server.js and paste the web server code below into the server.js file.
vi server.js
img


## Step 3: Install Express and set up routes to the server
*sudo npm install express mongoose*
img

In ‘Books’ folder, create a folder named apps
*mkdir apps && cd apps*

Create a file named routes.js and paste the code below into routes.js
*vi routes.js*
img

In the ‘apps’ folder, create a folder named models
*mkdir models && cd models*

Create a file named book.js and paste the code below into ‘book.js’
*vi book.js*
img


## Step 4 – Access the routes with AngularJS
Create a folder named public
*mkdir public && cd public*

Add a file named script.js and paste the Code below (controller configuration defined) into the script.js file.
*vi script.js*
img

In public folder, create a file named index.html and paste the code below into index.html file;
*vi index.html*
img

Change the directory back up to Books and Start the server by running this command:
*node server.js*

Open TCP port 3300 in your AWS Web Console for your EC2 Instance. accessing our Book Register web application from the Internet with a browser using Public IP address or Public DNS name.
img
img


