# How to connect to MariaDB using ODI 12c

To connect to MariaDB using Oracle Data Integrator (ODI) 12c, you'll need to configure a Data Server in ODI. Follow these steps to establish the connection:

Install the MariaDB JDBC Driver:
Before setting up the connection in ODI, make sure you have the MariaDB JDBC driver (JAR file) installed. If you don't have it, you can download it from the official MariaDB website or the Maven repository.

Configure the JDBC Driver in ODI:
Once you have the MariaDB JDBC driver, you need to add it to the ODI configuration.

Open the ODI Studio (Designer) client.

In the Top menu, go to "Help" > "About" > "Properties" > "Java Properties".

In the "Java Properties" window, click on "Add External JARs" and select the MariaDB JDBC driver JAR file.

Restart ODI Studio for the changes to take effect.

Create a Data Server:

Open the ODI Studio.

Go to "Topology" tab (usually located at the bottom-left corner).

Right-click on "Physical Architecture" and choose "New Data Server."

In the "Name" field, give your Data Server a meaningful name (e.g., "MariaDB_Server").

In the "JDBC URL" field, specify the connection details in the following format:

php
Copy code
jdbc:mysql://<hostname>:<port>/<database_name>
Replace <hostname>, <port>, and <database_name> with the appropriate values for your MariaDB instance.

In the "Driver" dropdown, select the MariaDB JDBC driver you configured earlier.

Enter the database credentials (username and password) in the respective fields.

Test the connection by clicking on the "Test Connection" button. Make sure the test is successful.

Click "Save" to save the Data Server.

Create a Physical Schema:

In the "Physical Architecture" section of the "Topology" tab, right-click on "Physical Schema" and choose "New Physical Schema."

Give your Physical Schema a name (e.g., "MariaDB_Schema").

In the "Data Server" dropdown, select the Data Server you created in the previous step.

Click "Save" to save the Physical Schema.

Create a Logical Schema:

In the "Topology" tab, navigate to the "Logical Architecture" section.

Right-click on "Logical Schema" and choose "New Logical Schema."

Give your Logical Schema a name (e.g., "MariaDB_Logical_Schema").

Under "Physical Architecture," select the Physical Schema you created earlier.

Click "Save" to save the Logical Schema.

Create a Model:

Now, you can create a new Model in the "Designer" tab.

Choose "File" > "New" > "Model."

Select "Relational" as the model type.

Choose the Logical Schema you created in the previous step.

Click "OK" to create the model.

Reverse Engineer the Database:

Right-click on the newly created Model and choose "Reverse Engineer."

ODI will connect to the MariaDB database using the configuration you provided and retrieve the metadata.

Perform your Data Integration tasks:

With the Model set up, you can now use ODI to perform various data integration tasks like designing mappings, transformations, and orchestrating workflows between different data sources.
