# phpadmindashboard

## Step 1 - Installing PHPMyAdmin 
   ```sudo apt update```
   
   ```sudo apt install phpmyadmin php-mbstring php-zip php-gd php-json php-curl```
   
  
  Using this command we installed the following packages:

php-mbstring: A module for managing non-ASCII strings with different encodings
php-zip: An extension that facilitates uploading .zip files to phpMyAdmin
php-gd: Enables support for GD graphics library
php-json: Provides support for JSON serialization
php-curl: Allows PHP to communicate with other servers
While installing PHPMyAdmin you will see a prompt that will ask you to select the webserver. Press <Spacebar> <Tab> and then enter key to continue the installation.
You will also be asked to continue with dbconfig-common setup. Press enter to confirm.
  
## Step 2 - Configuring a non-root user in MySQL
   
   ```sudo mysql```
   

  Since its not a good idea to use root as your login user, we will create another MySQL user named harry to login to the PHPMyAdmin console:

Execute the following query:

    CREATE USER 'harry'@'localhost' IDENTIFIED WITH caching_sha2_password BY '<your_passwprd>';
    
This creates a user named harry with the password - 'your_password'

Let's provide this user all the privileges so that we can use it to access the PHPMyAdmin console. Execute the query below

    "GRANT ALL PRIVILEGES ON *.* TO 'harry'@'localhost' WITH GRANT OPTION;"
You can now exit the MySQL shell:

"exit"


  ## Step 3 - Accessing phpMyAdmin 
Go to the browser and type 'http://your_domain_or_IP/phpmyadmin' in your URL bar. 
You will see an option to log into your PHPMyAdmin console. 
  Enter the username (harry in my case) and password you chose for this user. 
