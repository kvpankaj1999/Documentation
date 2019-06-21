# Documentation

This is the documentation for the Annotator App, The Viewer, setting up the database for the following applications and the Metabase dashboard for analysing data and sharing it with everyone.

### Setting up the Database

* This will be the database for serving the Annotation App, The Viewer and the Metabase dashboard.
* The tables in the database will be :
  * bookmarks
  * corrections
  * imagelinks
  * info
  * puids
  * ruids
  * uids
  * users
  * viewer
 * First download MYSQL from https://www.mysql.com/downloads/
 * Set up with a Username and Password for MYSQL.
 * Login into the MYSQL command line and create a database using the following command
    
       CREATE DATABASE databasename;
  
 * Here is the .sql file containing the schema of the database. Copy the tables from this sql file to the database created.
 * Using SQL insert into the tables the data that you have.
 * This database contains the schema of all the tables mentioned above and is now ready for the applications.
 
###  How to setup the Annotation App
This is the app which serves the front-end web-based annotation interface and manages the back-end DB in our HInDoLA system. 

* Set up the database as shown above.
* In the Annotation_app folder open the app.py file and change the database name to the name which was created. Also change the username name and password in the app.py file to the ones which were created while setting up the database.

#### * To setup the backend server on local system
1. Download the repository and install the prerequisites mentioned in Annotation_App/requirements.txt using the command:
      
        pip install -r requirements.txt
2. Go to the Annotation_App folder and locate app.py
3. Run ```python3 app.py ```

The Annotation App is to manage the manuscripts annotations through an interactive GUI. Implemented in Flask, the App has useful features to annotate images from large manuscripts libraries.

#### * Annotations
1. Open the page at the started local server
2. Sign-up and login
3. Request image through "Request" Button
4. Annotate with the regions provided - Freehand (single click to start and double click to finish), Polygon(Single click     to start, each click adds new vertex and double click to finish)
5. "Done" button to save the annotations, "Skip" button to skip the image 


### How to setup the Viewer

Viewer is used for viewing the annotated, the unannotated images done by the users and also to bookmark them for later use.
* Download or clone the Viewer repository and go to the folder containing the requirements.txt file.

* Use this command for installing all the requirements at once:

      pip install -r requirements.txt

* Connect your database containing all the tables and the information about the images to the application by changing the app.py file in the this folder: test\testingtool\tmp .

* Change the host to "localhost" in the app.py file. 

* After setting up the database and connecting it to the application, run the above app.py file using:

      python app.py .

 * Now in your browser go the site localhost:portnumber.
 
 ### How to setup the Metabase Dashboard
 
* The dashboard used for monitoring the backend databases is Metabase. This can be downloaded [here](https://metabase.com/start/jar.html).
* Take the database files that store all the information related to graphs,histograms,databases of the application which you are running and place them in the same folder as the metabase application downloaded above.

* To run Metabase, you will need to have Java8 or above install in your system. 
  For more information on setting up Metabse refer to this https://metabase.com/docs/latest/

* To run the dashboard,
- Logon to the server
- Goto the folder containing the database files of your application and save 'metabase.jar' in the same folder. 
- Run the command 'java -jar metabase.jar' in Command prompt(Windows) or Terminal(linux or Mac).

* But this will start the server on the default port:3000, to change port to say '56000', run the command
'export MB_JETTY_PORT=56000' before starting the dashboard. 

* By default the server starts as localhost i.e., 127.0.0.1, to change that run the command
  'export MB_JETTY_HOST=yourIP' before starting the dashboard.


  
