---
sidebar_position: 2
---

# Web Modules
- It takes number of iterations and the activity name that is to be performed.
- It displays the real-time graphs of the received data.
- It has start and stop buttons which starts receiving the data and plotting it and upon pressing the stop button it stores data in csv
- It uses flask for backend
- A custom API is also made


## Detailed Explanation


### Importing Libraries:
The following libraries are imported in the code:
- datetime: To work with dates and times
- Flask: To build the web application
- Flask_Cors: To handle Cross-Origin Resource Sharing (CORS)
- csv: To work with CSV files
- os: To handle file operations
- Application Initialization:

A Flask application is initialized with the following code:

 ```jsx title="App.py"

app = Flask(_name_)
CORS(app)
```

### Global Variables:
The following global variables are defined in the code:
- save_data: A flag to indicate whether data collection is in progress or not
- activityName: The name of the activity being performed
- examples: The number of examples recorded
- count: A counter
- dataQueue: A queue to store the incoming data from the sensors
Accelerometer, Gyroscope, Magnetometer, LinearAcceleration, Gravity: Lists to store data from different sensors
### Route Definitions:
The following routes are defined in the code:
- /: The default route which returns the index.html file.
- /sensors: A POST route to receive sensor data and append it to the dataQueue.
- /startRecord: A GET route to start data collection.
- /stopRecord: A GET route to stop data collection and save the data to a CSV file.
- /getData: A GET route to retrieve data from the dataQueue.
### Saving Data to a CSV file:
The SaveDataInCSV() function is used to save the data to a CSV file. The function creates a folder for the activity, with a subfolder for each example recorded. The data from each sensor is saved in a separate CSV file.