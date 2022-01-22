# MEAN STACK DEPLOYMENT TO UBUNTU IN AWS
MEAN Stack is a combination of following components:
1. MongoDB (Document database) – Stores and allows to retrieve data.
2. Express (Back-end application framework) – Makes requests to Database for Reads and Writes.
3. Angular (Front-end application framework) – Handles Client and Server Requests
4. Node.js (JavaScript runtime environment) – Accepts requests and displays results to end user


## Step 1: Install NodeJs
Update ubuntu:
*sudo apt update*

<img width="798" alt="Sudo apt update" src="https://user-images.githubusercontent.com/51254648/150649962-ca6f03e1-864b-4ce0-8cda-4df62cd32145.png">

Upgrade ubuntu:
*sudo apt upgrade*

<img width="1267" alt="sudo apt upgrade" src="https://user-images.githubusercontent.com/51254648/150649969-358d61d9-0a55-4309-8ee6-8617c2c80cde.png">


Add certificates:
*sudo apt -y install curl dirmngr apt-transport-https lsb-release ca-certificates*

<img width="849" alt="certificate 1" src="https://user-images.githubusercontent.com/51254648/150649973-ae9a2dab-31b4-4365-8e42-6bb9829ccd38.png">

*curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -*

<img width="1126" alt="certificate 2" src="https://user-images.githubusercontent.com/51254648/150649975-f00d11d8-264b-4e22-a487-91293412665d.png">


Install NodeJS:
*sudo apt install -y nodejs*

<img width="776" alt="install nodejs" src="https://user-images.githubusercontent.com/51254648/150649979-8c8e360e-ceb4-4487-88ff-647852eaaf38.png">


## Step 2: Install MongoDB:
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 0C49F3730359A14518585931BC711F9BA15703C6

echo "deb [ arch=amd64 ] https://repo.mongodb.org/apt/ubuntu trusty/mongodb-org/3.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.4.list

<img width="1276" alt="mongo package" src="https://user-images.githubusercontent.com/51254648/150649980-f5d4d8ac-d377-4a40-9043-98d3236a45c4.png">


Install MongoDB:
*sudo apt install -y mongodb*

<img width="1280" alt="install mongodb" src="https://user-images.githubusercontent.com/51254648/150649982-8c39966d-b71f-4b61-9b6d-aa3cc0aa7b05.png">


Start The server:
*sudo service mongodb start*

Verify that the service is up and running:
*sudo systemctl status mongodb*

<img width="686" alt="mongodb status" src="https://user-images.githubusercontent.com/51254648/150649986-1a2a6827-3682-4c81-b002-9fe035306be4.png">


Install npm – Node package manager:
*sudo apt install -y npm*

<img width="473" alt="package manager" src="https://user-images.githubusercontent.com/51254648/150649989-01496255-3736-4199-83d5-41716e110040.png">


Install body-parser package
We need ‘body-parser’ package to help us process JSON files passed in requests to the server:

*sudo npm install body-parser*

<img width="608" alt="install body parser" src="https://user-images.githubusercontent.com/51254648/150649990-52ba73ed-9216-4d03-b515-9f9170811770.png">


Create a folder named ‘Books’:
*mkdir Books && cd Books*

In the Books directory, Initialize npm project:
*npm init*

<img width="565" alt="npm init" src="https://user-images.githubusercontent.com/51254648/150649991-1ae16105-0e7b-4af2-8e39-64dbabdcac3c.png">

Add a file to it named server.js and paste the web server code below into the server.js file:
vi server.js

<img width="475" alt="web server code" src="https://user-images.githubusercontent.com/51254648/150649993-f11dfd12-f6b6-4a06-a351-b10c4c2d094c.png">



## Step 3: Install Express and set up routes to the server:
*sudo npm install express mongoose*

<img width="569" alt="install express mongoose" src="https://user-images.githubusercontent.com/51254648/150649994-d538f732-4f3e-4c90-ab6a-aac9bfce5d66.png">


In ‘Books’ folder, create a folder named apps:
*mkdir apps && cd apps*

Create a file named routes.js and paste the code below into routes.js:
*vi routes.js*

<img width="488" alt="routesjs code" src="https://user-images.githubusercontent.com/51254648/150649996-4911e5bd-d58a-49df-bb2f-fffb49ced4e1.png">


In the ‘apps’ folder, create a folder named models:
*mkdir models && cd models*

Create a file named book.js and paste the code below into ‘book.js’:
*vi book.js*

<img width="389" alt="bookjs code" src="https://user-images.githubusercontent.com/51254648/150649997-7bf5d7b0-4334-4f05-8cff-1d111b094220.png">



## Step 4 – Access the routes with AngularJS
Create a folder named public:
*mkdir public && cd public*

Add a file named script.js and paste the Code below (controller configuration defined) into the script.js file:.
*vi script.js*

<img width="375" alt="scriptjs code" src="https://user-images.githubusercontent.com/51254648/150650001-41496871-3a11-4956-9cee-a28c8de1594c.png">


In public folder, create a file named index.html and paste the code below into index.html file;
*vi index.html*

<img width="699" alt="indexhtml code" src="https://user-images.githubusercontent.com/51254648/150650003-8bf2376c-5238-45ae-acb5-fd3245e5e72b.png">


Change the directory back up to Books and Start the server by running this command:
*node server.js*

Open TCP port 3300 in your AWS Web Console for your EC2 Instance. accessing our Book Register web application from the Internet with a browser using Public IP address or Public DNS name.

<img width="429" alt="Book Register web app" src="https://user-images.githubusercontent.com/51254648/150650006-9d5b010d-fd6a-47c9-9b17-87688599ad4e.png">

<img width="1272" alt="Book register app shell" src="https://user-images.githubusercontent.com/51254648/150650007-16dd09e5-a34a-488d-9aec-fc76ead5654e.png">

