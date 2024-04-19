To get this code to work you will need a few things.
Install Docker Hub, its an application.
Install Mongo DB compass application
Install Postman application
Highly recommend creating a virtual enviroment and then install the below packages
Here is the commands to create and activate the virtual enviroment: 
Command 1: python -m venv myenv  Command 2: source myenv/bin/activate 

pip install fastapi motor bson
Run this command when you ready to test the code : docker run --name some-mongo -p 27017:27017 -d mongo
Run this command next to activate the fast api: uvicorn main:app --reload 
Open up MongoDB Compass and click connect, look for expense tracker database on the left side
You will need to open postman up to test if the code works but sumbitting information to the database, I can show that to everyone in person.
