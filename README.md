# Experiment 5: Displaying Notifications in Android

**Name:** Tejas Sunil Waske  
**USN:** 25MCAR0189

## Aim
To develop an Android application for displaying notifications in Android.

## Concept / Technology
Notifications are messages displayed outside the app's UI to alert users. From Android 8.0 (API 26), notifications must be posted through a **Notification Channel**. From Android 13 (API 33), apps must request the runtime permission `POST_NOTIFICATIONS`. `NotificationCompat.Builder` is used to construct the notification (icon, title, text), and `NotificationManagerCompat` displays it.

## Scenario
The app has a single button "Show Notification". On click, the app checks/requests the POST_NOTIFICATIONS permission (for Android 13+), then builds and displays a notification with a title and message in the system notification tray.

## Project Structure

NotificationDemo/
├── app/
│ ├── src/main/
│ │ ├── java/com/example/notificationdemomad5/
│ │ │ └── MainActivity.kt # Creates channel, handles permission, sends notification
│ │ ├── res/layout/
│ │ │ └── activity_main.xml # Button UI
│ │ └── AndroidManifest.xml # POST_NOTIFICATIONS permission declared
│ └── build.gradle.kts
└── README.md

## Output
<img width="1080" height="2358" alt="screenshot5 png" src="https://github.com/user-attachments/assets/3b4aac2f-7a31-4c7a-8781-22f854598b2b" />


## Test Cases

### Test Case 1: Permission Request
**Steps:** Open app on Android 13+ device → Click "Show Notification".  
**Expected Result:** System permission dialog appears asking to allow notifications.  


### Test Case 2: Notification Displayed
**Steps:** Allow the permission → Notification appears in the notification tray.  
**Expected Result:** Notification with title "Hello!" and message is visible when swiping down the status bar.  


### Test Case 3: Verification with Name and USN
**Steps:** App screen/notification content displaying Name: Tejas Sunil Waske, USN: 25MCAR0189 to confirm authorship.  
**Expected Result:** Name and USN visible on screen/notification.  


## Conclusion
This experiment demonstrates creating a Notification Channel, building a notification using NotificationCompat, and handling runtime notification permission for Android 13+.
