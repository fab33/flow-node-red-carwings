# flow-node-red-carwings
This flow is written to use with node-red to retrieve data from NISSAN Leaf and control climate.
I prefer to write a flow because, it's easier to maintain.
You have to add crypto javascript library because I can't find node providing blowfish ECB function. Feel free to open issue or contact me if you hear about a such node.

You have to enter your carwings credentials in "user value" node in the sub-flow "Login and create session"
Timeout for an update from the car is set to 120s but can be change in "Max retries" node.

Results are published on following MQTT Topic :
- base_topic/state : busy, done, error depending on last status. Actually, I didin't log error cause, but it's quite simple to add
- base_topic/BatteryStatusRecords : a JSON object with all the data from the carwings API

![Screenshot](screenshot.png)
