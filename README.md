# REST API Tutorial with JWT & Node.js


## Before using

- Please make sure that you have:
 - node.js installed (https://nodejs.org/)
 - have mongodb installed and running locally (https://www.mongodb.com/)
   - Using Windows, just open the terminal at where you installed mongo and run `mongod.exe`
 - run npm install in your root project folder
## Usage

To run the project, please use a command line the following:
 - npm start
    - It will run the server at port 3600.
    
    
  Api method for check using POSTMAN  
  
  
http://localhost:3600/users/
CREATE USER IN MONOGDB DATABASE
method : POST 
Headers:
    Accept:application/json
	Content-Type:application/json
	Body json -
	{
	   "firstName" : "suraj",
	   "lastName" : "sah",
	   "email" : "surajs@gmail.com",
	   "password" : "123456"
	}	

Response : {
    "id": "5cfa4454c9860a6cd4163832"
}
--------------------------------------------------------------------------------------------------------------
http://localhost:3600/auth/

GENERATE TOKEN FOR SECURITY
method : POST 
Headers:
    Accept:application/json
	Content-Type:application/json
	Body json -
	{
	   "email" : "surajs@gmail.com",
	   "password" : "123456"
	}

Response : {
    "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiI1Y2ZhM2U4M2M5ODYwYTZjZDQxNjM4MzEiLCJlbWFpbCI6InNhaHN1cmFqQGdtYWlsLmNvbSIsInBlcm1pc3Npb25MZXZlbCI6MSwicHJvdmlkZXIiOiJlbWFpbCIsIm5hbWUiOiJzdXJhamQgc2FoZCIsInJlZnJlc2hLZXkiOiJScEtKTkFjOE0zWElSbjBhL3IrMWNRPT0iLCJpYXQiOjE1NTk5MDUzOTl9.dGA9NGZMu0UbYTccIsGQGwIx0A0kb74eLsj8DfnRCaE",
    "refreshToken": "QTY2OERCdGRpV0FGYmRCK3lMTnE0ZHgrSXFsK1lndGc3anBhMFF1TXNSVCtSZXZGOHRpUWVYNjFhdittTXZod3E3V0o4ZTNaTy9UU1RxZkFZSmcwdkE9PQ=="
}

--------------------------------------------------------------------------------------------------------------
http://localhost:3600/users/5cfa3d50c9860a6cd4163830
GET USER DATA
	postman testing process
	method : GET
	Headers -
	Accept:application/json
	Content-Type:application/json
	Authorization:Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9   (valid token pass here)

--------------------------------------------------------------------------------------------------------------
http://localhost:3600/users/5cfa3d50c9860a6cd4163830
	UPDATE USER DATA
	postman testing process
	method : PATCH
	Headers -
	Accept:application/json
	Content-Type:application/json
	Authorization:Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9   (valid token pass here)
	-------------------for update user firstname and lastname 
	Body - {
	"firstName" : "surajs",
	"lastName" : "sahs"
}

--------------------------------------------------------------------------------------------------------------
http://localhost:3600/users/5cfa3d50c9860a6cd4163830
	DELETE USER DATA
	postman testing process
	method : DELETE
	Headers -
	Accept:application/json
	Content-Type:application/json
	Authorization:Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9   (valid token pass here)
