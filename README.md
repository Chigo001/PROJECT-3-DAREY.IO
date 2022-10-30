STEP 5: PROJECT 3 MERN STACK IMPLEMENTATION
- SIMPLE TO-DO APPLICATION ON MERN WEB STACK
- MERN Web stack consists of the following;
- MONGODB
- EXPRESSJS
- REACTJS
- NODE.JS
- The first thing to do is to create a new EC2 instance with Ubuntu Server 20.04 LTS (HVM)

STEP 1 BACKEND CONFIGURATION
- Update sudo apt
<img width="1440" alt="Screenshot 2022-10-25 at 5 13 47 PM" src="https://user-images.githubusercontent.com/115854902/198850835-bb796fc0-ee08-4e04-9457-e6e315cf5e1f.png">

- Upgrade Ubuntu
<img width="753" alt="Screenshot 2022-10-25 at 5 15 45 PM" src="https://user-images.githubusercontent.com/115854902/198852239-52f2d3e9-aefa-47df-bd9b-e97fdeced4e2.png">


- Get the location of Node.js software from Ubuntu repositories
<img width="1440" alt="Screenshot 2022-10-25 at 5 18 42 PM" src="https://user-images.githubusercontent.com/115854902/198852008-461893eb-ce64-4f71-8ead-4b132a803e36.png">

- Install Node.js and npm
- Verify the node installation 
- APPLICATION CODE SETUP
- I created a new directory for my TO-Do project
- Verify the Todo directory is created 
- cd Todo
- I created a new file named package.json in my Todo file
- Verify that you have the package.json file created 

<img width="1440" alt="Screenshot 2022-10-25 at 5 25 36 PM" src="https://user-images.githubusercontent.com/115854902/198852705-7b81387a-021b-4335-a139-e94e460b0089.png">

<img width="1440" alt="Screenshot 2022-10-25 at 5 32 53 PM" src="https://user-images.githubusercontent.com/115854902/198852724-a3233e8b-96f5-45e2-b1ae-2f9bf3e86ec7.png">

INSTALL EXPRESSJS
- Install express
- Then, i created a file named index.js
- I confirmed index.js is successfully created
- Next step was to install the dotenv module
- Open the index.js file
- Type code given into the index.js file and save.
- Then i went ahead to start my server to ensure it was running on port 5000 in my terminal.
<img width="1440" alt="Screenshot 2022-10-25 at 5 52 11 PM" src="https://user-images.githubusercontent.com/115854902/198867842-f62cde88-4cf4-44d1-aa5e-82c3d85555f8.png">

- Next step was to go to my EC2 security groups, then create an inbound rule to open TCP port 5000
<img width="1440" alt="Screenshot 2022-10-30 at 9 00 21 AM" src="https://user-images.githubusercontent.com/115854902/198868592-2b9742da-9bee-4574-bd0e-e911f3fb7407.png">

Open browser to access public IP followed by port 5000 (http://public IP:5000)
<img width="1440" alt="Screenshot 2022-10-25 at 5 58 29 PM" src="https://user-images.githubusercontent.com/115854902/198868762-9a381012-a19a-49ae-b145-6a6cd1f40588.png">

- Next step was to create a routes folder to define various endpoint 
- Then, change directory to route folder
- Create a file api.js
- Open the file then copy and paste the code given.

<img width="1440" alt="Screenshot 2022-10-25 at 6 33 13 PM" src="https://user-images.githubusercontent.com/115854902/198869003-4fdee69d-16c3-4d9c-bb31-0841fa8daaf7.png">

MODELS

A model is at the heart of Java-Script based applications and this is what makes it interactive. We will also be using Models to define the database schema.
- I created a schema and a model by installing Mongoose which is a Node.js package. I changed the directory back to Todo before installing mongoose
- I created a new folder Models
- Next, I changed directory into the models folder with cd models.
- Then i went ahead to create a file inside the models folder and named it todo.js
- I pasted the code given into the file i created with 'vim todo.js'.
- In the Routes directory, i opened api.js file, deleted previous content then pasted the code given, then went ahead to save and exit. I also verified the file by running cat api.js on the terminal.
<img width="1440" alt="Screenshot 2022-10-25 at 10 06 40 PM" src="https://user-images.githubusercontent.com/115854902/198869720-05613b93-4b23-4ef2-aad2-1996357d2ed0.png">

MONGODB DATABASE
- Mlab will be providing us with a MongoDB database as a service solution.
- so we will sign up, select AWS as the cloud provider then allow access to MongoDB database from anywhere .(This is not secure but it is for development and not production).
- It is important to change the time of deleting the entry from 6hrs to 1week.
- Create a MongoDB database by creating a new cluster then add username, allow to readwriteAnyDatabase and then password .
<img width="1440" alt="Screenshot 2022-10-29 at 4 41 57 PM" src="https://user-images.githubusercontent.com/115854902/198870346-de540f04-44b8-472b-b761-639a5c2e69b7.png">

- Next, create a file in the Todo directory and name it .env
- Then I added the connection string to access the database by updating the username, network-address and database name from my cluster set up.
- I went ahead to update the index.js file to reflect the use of .env so that Node.js can connect to the database.
- I opened the file with 'vim index.js' deleted it's previous content then pasted the code given, then saved and exit.
- I started my server using the command 'node index.js' to confirm database has been connected successfully but i had a blocker here as I got an error on terminal which had to do with my cluster password and i rectified it by using the autogenerated password and my database connected successfully .
<img width="1440" alt="Screenshot 2022-10-27 at 4 09 40 PM" src="https://user-images.githubusercontent.com/115854902/198871174-21e1e7f1-901a-4140-9515-419787ea2c34.png">

- The next step was to test our Backend code without Frontend using Restful API.
- In this project, we will use Postman to test our API
- INSTALL AND DOWNLOAD POSTMAN
- Open Postman and create a Post, request to the API. (http://<public IP>:5000/api/todos.
- Ensure to set header key Content-Type as application/json
- On the Body, we will type in records for our Todo application.
- Then i went ahead to create a GET request.
- I tested all the API endpoints to make sure they were working.
- We have successfully created our Backend.

<img width="1440" alt="Screenshot 2022-10-27 at 11 15 44 PM" src="https://user-images.githubusercontent.com/115854902/198871561-65d7f351-7294-429f-804c-5ed0ff0b9ddf.png">
<img width="1440" alt="Screenshot 2022-10-27 at 11 19 57 PM" src="https://user-images.githubusercontent.com/115854902/198871571-5bf98da4-07bd-484d-865b-02a883042dc9.png">

STEP 2 FRONTEND CREATION
- To start out with the frontend of the To-do app, we will use the create a new folder in our Todo directory called client,where we will add all the react code.
<img width="1440" alt="Screenshot 2022-10-27 at 11 31 35 PM" src="https://user-images.githubusercontent.com/115854902/198872430-c2190cff-2501-4027-8747-eb795324e8f6.png">

- Install Concurrently in order to run more than one command from the same terminal
<img width="1440" alt="Screenshot 2022-10-27 at 11 34 54 PM" src="https://user-images.githubusercontent.com/115854902/198872529-44977b5c-c937-483c-b4bc-3134f2ef3363.png">

- Install nodemon, this will be used to monitor the server
<img width="1440" alt="Screenshot 2022-10-27 at 11 36 04 PM" src="https://user-images.githubusercontent.com/115854902/198872606-d29c8fd8-b9ba-43a8-99e7-697246707a7a.png">

- Next we will open the package.json file in our Todo folder, we will change the highlighted part and replace with the code given,save and exit. Then confirm with cat.package.json on the terminal
- CONFIGURE PROXY IN PACKAGE.JSON
- To confirm proxy in package.json, change directory to client. 'cd client'
- Open the package.json file
- Then add the key value pair in the file 'proxy'. "http://localhost:5000".
- In the Todo directory run "npm run dev" your app should open and start running on localhost:3000
<img width="1440" alt="Screenshot 2022-10-28 at 1 49 01 PM" src="https://user-images.githubusercontent.com/115854902/198873028-505af41f-18c1-4cb1-a169-37bad0287862.png">

In order to access the application on the internet, I opened TCP port 3000 on my EC2 instance by adding a new security group rule.
<img width="1440" alt="Screenshot 2022-10-28 at 1 56 51 PM" src="https://user-images.githubusercontent.com/115854902/198873083-a1b14732-9603-46ce-b73e-c91fd53e3498.png">

CREATING OUR REACT COMPONENTS
React makes use of components that are reuseable and also makes code modular. From our Todo directory run cd client 
- Move to the src directory
- Inside the src folder create another folder called components.
- cd components 
- Inside 'components' directory create 3files  Input.js, ListTodo.js and Todo.js
- Open input.js file and copy and paste the codes given.
- We will be making use of Axios which is a promise based HTTP client for the browser and node.js
- Move to src folder by cd.. on your terminal.
- Move to clients folder cd..
- Install Axios
- Go to 'components' directory
- After that open your ListTodo.js
- In this ListTodo.js copy and paste the following code, save and exit.
- Then in the Todo.js file write the following code, save and exit.
- Move to the src folder cd..
- Ensure you are in the src folder and run vi. App.js
- Copy and paste the code given, save and exit.
- In the src directory, open the App.css then paste the code given into the App.css, save and exit.
- In the src directory, open the index.css then copy and paste the code given, save and exit.
- Go to the Todo directory cd../..
- In the Todo directory run: "npm run dev".

<img width="1440" alt="Screenshot 2022-10-28 at 2 09 04 PM" src="https://user-images.githubusercontent.com/115854902/198875345-47bb9f13-b785-4175-946d-9e6ce18e93f6.png">

My Todo app is fully functional and is able to create a task view all task and delete a task.

<img width="1440" alt="Screenshot 2022-10-28 at 2 36 45 PM" src="https://user-images.githubusercontent.com/115854902/198875499-b32f67bc-9550-4268-b016-8ae1eca28c8d.png">

<img width="1440" alt="Screenshot 2022-10-28 at 2 38 37 PM" src="https://user-images.githubusercontent.com/115854902/198875508-a59e5ef8-158c-47c4-8e50-cc2ee60df58d.png">

CREDITS:
1. This guide was inspired by Digital Ocean
2. Educative.io




