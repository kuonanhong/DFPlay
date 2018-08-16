
## DoorAlarm.ino

This example presents a typical IOT use case to demonstrate how DFPlay can be used to generate audible alarms / notifications as events occur.

DoorAlarm.ino monitors the state of an imaginary door. The door sensor has been replaced by a Particle Function that allows you to toggle the door's state by typing "open" or "closed" and pressing the CALL button. 

This is how the Particle Function is displayed in the Particle Console.  The "2" represents the return value, which represents the door's state (open = 1, closed = 2). 
![](https://lh4.googleusercontent.com/uxTKFDygRYJ8ZTqSAmZRp07joTP_uoALhVQuC8eOHSslC6xkrPR8gkuPU4cOqdwCQEU3Z1EQ_7lVXVMcxnAs5IoMuAk0vSP1EyBHGSe4wQVMe2x9n3TqQxLuhhXwRRDwOGRO6to2)

DoorAlarm.ino is designed to play two sounds:
- One sound will play when the door’s status changes from "open" to “closed”.
- Another sound will play when the door's status changes from "closed" to "open" and that sound will repeat every five minutes until the door returns to the closed state.    

### Preparing to use this Example:  

By default, the example plays: the following tracks to create the sounds.
-   SD, Folder 16, Track 1 when the door opens. 
-   SD, Folder 16, Track 2 when the door closes.
    
You can either place the tracks that you want to play in these locations or you can change the following two lines of code to reflect other locations.
``` cpp
Selection doorOpen = {2,16,1,0,0};
Selection doorClosed = {2,16,2,0,0};
```
Please consult the DFPlay QuickStart Guide if you need more information about how to configure Selections.

### Running the Example:

 1. Flash your Particle device with the DoorAlarm.ino code.
 2. Bring up the Particle Console for your device.
 3. Type "closed", click CALL, and the doorClosed track should play.
 4. Type "open", click CALL, and the door Open track should play every five minutes ... until the door closes. 

Comments were inserted in the code to assist those who may wish to modify volume, the delay between notifications, or other settings.

You could select a long track to play when the door is open, and have it repeat.

> Written with [StackEdit](https://stackedit.io/).