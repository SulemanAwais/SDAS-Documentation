---
sidebar_position: 1
---

# Android App Module
## UI Module:
- It takes input from the user about IP Address
- It shows the sensors data of the mobile device in the text fields.
## Sensor Data Acquiring Module:
- It retreives the data of listed sensors of the mobile device i.e., Accelerometer etc.
- Timestamps are also recorded here
## Data Sending Module:
**send()** method is invoked here and HTTP request is generated which sends the acquired data to the given IP address
 ### Detailed Explanation:
  
The code starts by importing various required packages such as **android.annotation.SuppressLint, android.hardware.Sensor, android.hardware.SensorEvent, android.hardware.SensorEventListener, android.hardware.SensorManager, android.os.Bundle, android.widget.Button, android.widget.TextView, and android.widget.Toast.** The code also imports various Volley packages for handling HTTP requests.

The class **MainActivity** extends AppCompatActivity and implements the SensorEventListener interface. This class contains various instance variables such as SensorManager object, List **Sensor** object, RequestQueue object, and various TextView objects to display the values of each sensor. The class also contains various float variables to store the values of each sensor.

The onCreate method is the first method that is called when the activity is launched. In this method, the content view of the activity is set using the setContentView method. The method then initializes the sensor manager using getSystemService method and creates a list of sensors. It checks if each of the required sensors is available and adds them to the list. It then displays the names of all sensors available in the device. The code then registers each of the sensors in the list using the registerListener method of the sensor manager.

The code then initializes various TextView objects for each sensor and sets the references to their respective XML elements. It also initializes a Button object for start and stop buttons. The startButton is used to start the sensors and the stopButton is used to stop the sensors.

The onSensorChanged method is called every time the values of the sensor change. In this method, the values of each sensor are updated and displayed in their respective TextView objects.

The code also includes methods for handling HTTP requests such as sendRequest and onResponse. These methods are used to send the sensor values to a remote server and handle the response from the server. The code includes a Toast to display a message when the data is sent to the server successfully.

 
