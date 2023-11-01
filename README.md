Smart Water Tank with online monitoring dashboard (Web GUI)

This is an IOT project implemented using Raspberry Pi and custom Web Application. I have revamped the Web Application code for better understanding.

As shown in the animation below, an ultrasonic sensor is fitted on top of the water tank. The sensor is connected to Raspberry Pi, which measures water level in the tank every minute. The water level reading is fed to a remote database. A Web Application running in the remote host makes use of this data to update the water level animation and the thin bar line graph.

![image](https://github.com/mayilaikaviya/IOT_Phase1/assets/146530348/62fd49b0-24a2-454d-a0d1-3d96d8b245b6)


How to use the code water-tank

This directory contains the code of Dashboard (Web GUI). It is required to be placed inside the public directory ("htdocs" or "www") of your webserver. You can install a Webserver such as XAMPP on your PC or Laptop and place 'water-tank' directory in 'htdocs' folder.

Create a database with name 'water_level' using phpmyadmin utility and import the "water_level.sql" database file (present in 'water-tank' directory).

Change the database connection settings in 'util.php' file as per your environment.

Open browser and go to this URL "http://127.0.01/water-tank". You should see the dashboard

raspberry-pi

Place this directory anywhere in your Raspberry Pi. This directory contains following files:-

'sample.py' : A test program to check if you are able to communicate with the Web Application.

![image](https://github.com/mayilaikaviya/IOT_Phase1/assets/146530348/f4b7f194-a352-4a42-8929-ef88faa235c5)


'sensor.py' : Actual code that interacts with the ultrasonic sensor and uploads the data to Web Application. 'setup_cron.sh': a bash script that helps you creating a cron task to run a python file through cron every minute. Edit the Web Server IP address in the python files as per the IP address of your Web Server.

Create a cron job which runs the file 'sensor.py' or 'sample.py' every minute. So that the selected file is automatically executed every minute to upload the data to Web Application.
