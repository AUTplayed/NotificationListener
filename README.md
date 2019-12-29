![image](https://i.imgur.com/MhISkDD.png)

This project consists of an android app, a java server and a chrome extension.

### Android app

The android app sends all current notifications whenever a new one gets added or one is removed to the server.
It also executes the pending actions supplied by the server.

### Server

The server acts as a relay between the chrome extension and the android app.
It saves the submitted notifications from the app and sends them to the chrome extension when requested.

It also receives actions from the chrome extension and sends them to the app as a response to the next notification update.

### Chrome extension

The UI. It displays the current notifications on the phone. Auto-updates every few seconds. 
Via the extension you can also send actions to the phone (currently just to dismiss a notification)


---

## Setup

The setup requires a password that is shared between every component.

- In the app it's right there when you open it, the password field on the bottom
- On the server it searches for a secret.secret file with just the password in the execution directory
- In the chrome extension you have to set the password via rmb on the extension -> options

The app has to be allowed notification access, for that open the android settings -> Notifications -> Notification access -> enable ListenerService
