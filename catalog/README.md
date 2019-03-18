# Itemcatalog
MATHI RAASI
This web app is a project for the Udacity FSND Course.

About
This project is a RESTful web application utilizing the Flask framework which accesses a SQL database that populates categories and their items. OAuth2 provides authentication for further CRUD functionality on the application. Currently OAuth2 is implemented for Google Accounts.
It provided with add ,delete,edit on categories .

In This Repo
This project has one main Python module main.py which runs the Flask application. A SQL database is created using the Data_Setup.py module and you can populate the database with test data using database_init.py. The Flask application uses stored HTML templates in the tempaltes folder to build the front-end of the application.Screenshots of my project function outputs are placed in a img folder. 
->Requirements:
1.Python
2.HTML
3.CSS
4.OAuth
5.Flask Framework
Installation
There are some dependancies and a few instructions on how to run the application. Seperate instructions are provided to get GConnect working also.

->Dependencies:
Vagrant(https://www.vagrantup.com/)
Udacity Vagrantfile(https://github.com/udacity/fullstack-nanodegree-vm)
VirtualBox(https://www.virtualbox.org/wiki/Downloads)
->How to Install:
1)Install Vagrant & VirtualBox
2)Clone the Udacity Vagrantfile
3)Go to Vagrant directory and either clone this repo or download and place zip here
4)Launch the Vagrant VM (vagrant up)
5)Log into Vagrant VM (vagrant ssh)
6)Navigate to cd/vagrant as instructed in terminal
7)The app imports requests which is not on this vm. Run sudo pip install requests
8)Setup application database python /Item_catalog/Data_Setup.py
	In this step database is successfully created.
9)*Insert fake data python /Item_catalog/database_init.py
	In this step data is inserted into the database sucessfully inserted.
	this can be understand by displaying the message like:
	Successfully Add First User
    Your papers database has been inserted!
	
10)Run application using python /Item_catalog/main.py
	
11)Access the application locally using http://localhost:8000
	after the successfull compile in command prompt .open the application using https://localhost:8000
*Optional step(s):

->Using Google Login
To get the Google login working there are a few additional steps:

1)Go to Google Dev Console(https://console.developers.google.com)
2)Sign up or Login if prompted
3)Go to Credentials
4)Select Create Crendentials > OAuth Client ID
5)Select Web application
6)Enter name 'News Paper Store' and upload a picture .
7)Authorized JavaScript origins = 'http://localhost:8000'
8)Authorized redirect URIs = 'http://localhost:8000/login' 
	and press Enter && 'http://localhost:8000/gconnect'and again press enter.
9)Select Create
10)Copy the Client ID and paste it into the data-clientid in login.html and in mainpage.html
11)On the Api Console Select Download JSON 
12)Rename JSON file to client_secrets.json
13)Place JSON file in Item_catalog directory that you cloned from here
14)Run application using python /Item_catalog/main.py
->JSON Endpoints:
The following are open to the public:

allPaperssJSON: '/PaperStore/JSON' - Displays the whole languages
and all items which are papers.

categoriesJSON: '/paperStore/paperCategories/JSON' - Displays all languages

itemsJSON: '/paperStore/papers/JSON' Displays  all papers items

categoryItemsJSON:	'/paperStore/<path:paper_name>/papers/JSON'-Displays papers for specific language

ItemJSON: '/paperStore/<path:paper_name>/<path:edition_name>/JSON' - Displays a specific paper item of particular language.