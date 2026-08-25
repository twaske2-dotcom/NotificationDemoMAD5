# Experiment 5: Displaying Notifications in Android

## Student Details

**Name:** Tejas Sunil Waske  
**USN:** 25MCAR0189  
**Experiment No.:** 5

---

## Aim

To develop an Android application for displaying notifications in Android.

---

## Objective

The objective of this experiment is to understand how notifications are created and displayed in an Android application using Notification Channels and NotificationCompat.

The experiment also demonstrates how runtime notification permission is handled for Android 13 and above.

---

## Concept / Technology Used

### Android Notifications

A notification is a message displayed outside the application's main user interface to inform or alert the user about an event or activity.

Notifications can be displayed in the Android system notification tray.

### Notification Channel

From Android 8.0 (API 26), notifications must be associated with a Notification Channel.

A Notification Channel allows users to control notification behavior and preferences for different types of notifications.

### NotificationCompat.Builder

`NotificationCompat.Builder` is used to construct the notification.

It can be used to specify:

- Notification title
- Notification message
- Notification icon
- Notification priority
- Other notification properties

### NotificationManagerCompat

`NotificationManagerCompat` is used to display the notification.

### POST_NOTIFICATIONS Permission

From Android 13 (API 33), applications need the runtime permission:

```text
POST_NOTIFICATIONS
```

The application requests this permission before displaying notifications.

---

## Scenario

The application contains a single button named:

```text
Show Notification
```

When the user clicks the button:

1. The application checks the notification permission.
2. On Android 13 and above, the application requests `POST_NOTIFICATIONS` permission if required.
3. A Notification Channel is created.
4. A notification is built using `NotificationCompat.Builder`.
5. The notification is displayed in the Android notification tray.

### Application Flow

```text
Open Application
       |
       ↓
MainActivity
       |
       ↓
Click "Show Notification"
       |
       ↓
Check Notification Permission
       |
       ├───────────────┐
       |               |
       ↓               ↓
Permission          Permission
Granted             Not Granted
       |               |
       |               ↓
       |        Request Permission
       |               |
       └───────┬───────┘
               ↓
      Create Notification
               |
               ↓
      Display Notification
               |
               ↓
      Android Notification Tray
```

---

## Software Requirements

- Android Studio
- Kotlin
- Android SDK
- Gradle
- Android Emulator or Physical Android Device

---

## Technologies Used

- Kotlin
- Android Notifications
- Notification Channel
- NotificationCompat.Builder
- NotificationManagerCompat
- Runtime Permission
- XML Layout
- Android Manifest
- Android SDK

---

## Project Folder and File Structure

```text
NotificationDemoMAD5/
│
├── app/
│   │
│   ├── src/
│   │   │
│   │   └── main/
│   │       │
│   │       ├── java/
│   │       │   └── com/example/notificationdemomad5/
│   │       │       └── MainActivity.kt
│   │       │
│   │       ├── res/
│   │       │   └── layout/
│   │       │       └── activity_main.xml
│   │       │
│   │       └── AndroidManifest.xml
│   │
│   └── build.gradle.kts
│
├── gradle/
│   └── wrapper/
│
├── .gitignore
├── build.gradle.kts
├── gradle.properties
├── gradlew
├── gradlew.bat
├── settings.gradle.kts
├── screenshot.png
└── README.md
```

---

## Important Files and Their Purpose

### MainActivity.kt

`MainActivity.kt` contains the main application logic.

It:

- Creates the Notification Channel.
- Checks notification permission.
- Requests notification permission on Android 13+ when required.
- Creates the notification.
- Displays the notification using `NotificationManagerCompat`.

---

### activity_main.xml

`activity_main.xml` defines the main user interface of the application.

The interface contains the **Show Notification** button used to trigger the notification process.

---

### AndroidManifest.xml

`AndroidManifest.xml` contains the application configuration and declares the notification permission required by the application.

The notification permission used is:

```text
android.permission.POST_NOTIFICATIONS
```

---

### build.gradle.kts

This file contains the Android application build configuration and project dependencies required to build and run the application.

---

## Working / Implementation

### Step 1: Launch Application

The application starts with `MainActivity`.

The main screen displays the **Show Notification** button.

---

### Step 2: Click Show Notification

When the user clicks the button, the application starts the notification process.

---

### Step 3: Check Permission

For Android 13 and above, the application checks whether notification permission has been granted.

If permission has not been granted, the application requests:

```text
POST_NOTIFICATIONS
```

---

### Step 4: Create Notification Channel

A Notification Channel is created for the application.

The channel is required for notifications on Android 8.0 and above.

---

### Step 5: Build Notification

The notification is created using:

```kotlin
NotificationCompat.Builder
```

The notification contains:

```text
Title: Hello!

Message: Notification displayed successfully.
```

---

### Step 6: Display Notification

The notification is finally displayed using:

```kotlin
NotificationManagerCompat
```

The user can view the notification by opening the Android notification tray.

---

# Test Cases

## Test Case 1: Permission Request

### Test Objective

To verify that the application requests notification permission on Android 13 and above.

### Test Steps

1. Open the application on an Android 13+ device or emulator.
2. Click the **Show Notification** button.
3. Observe the screen.

### Expected Result

The Android system should display a permission dialog asking the user to allow notifications.

### Actual Result

The notification permission dialog was displayed successfully.

### Status

**PASS ✅**

---

## Test Case 2: Notification Display

### Test Objective

To verify that the notification is displayed successfully after permission is granted.

### Test Steps

1. Open the application.
2. Click **Show Notification**.
3. Allow notification permission if requested.
4. Swipe down the notification panel.
5. Observe the notification.

### Expected Result

A notification containing the title and message should appear in the Android notification tray.

### Actual Result

The notification was displayed successfully in the notification tray.

### Status

**PASS ✅**

---

## Test Case 3: Verify Student Name and USN

### Test Objective

To verify the student's name and USN as part of the application submission.

### Test Data

**Name:** Tejas Sunil Waske

**USN:** 25MCAR0189

### Test Steps

1. Launch the application.
2. Use the application/notification screen where the student information is displayed.
3. Verify the student's name.
4. Verify the USN.

### Expected Result

The correct student name and USN should be displayed.

```text
Name: Tejas Sunil Waske
USN: 25MCAR0189
```

### Actual Result

The student's name and USN were verified successfully.

### Status

**PASS ✅**

---

# Output

The application successfully displays a notification using Android Notification APIs.

The application requests notification permission where required, creates a Notification Channel, builds the notification using `NotificationCompat.Builder`, and displays it through `NotificationManagerCompat`.

### Output Screenshot

<img width="732" height="1600" alt="screenshot501" src="https://github.com/user-attachments/assets/7c1a9def-2393-4a1d-b01f-72586f83762e" />
<img width="732" height="1600" alt="screenshot502" src="https://github.com/user-attachments/assets/496ab4de-d6f0-40f3-ab06-aebea90a726d" />




---

# Steps to Run the Project

1. Open the project in Android Studio.
2. Allow Gradle synchronization to complete.
3. Connect an Android device or start an Android Emulator.
4. Select the application from the Run Configuration.
5. Click the **Run ▶** button.
6. Launch the application.
7. Click the **Show Notification** button.
8. Grant notification permission if requested.
9. Swipe down the notification panel.
10. Verify that the notification is displayed.

---

# Requirements

## Hardware Requirements

- Laptop/Desktop
- Android Device or Android Emulator
- USB Cable if using a physical Android device

## Software Requirements

- Android Studio
- Kotlin
- Android SDK
- Gradle

---

# Learning Outcomes

After completing this experiment, the following concepts were understood:

- Android Notifications
- Notification Channels
- `NotificationCompat.Builder`
- `NotificationManagerCompat`
- Runtime notification permission
- `POST_NOTIFICATIONS`
- Android 13+ notification handling
- AndroidManifest.xml
- XML Layouts
- Displaying notifications in the Android notification tray

---

# Result

The Android application was successfully developed and executed to demonstrate the creation and display of notifications using Android notification APIs.

---

# Conclusion

The experiment successfully demonstrated how to create and display notifications in an Android application.

The application creates a Notification Channel, handles the `POST_NOTIFICATIONS` runtime permission for Android 13 and above, builds the notification using `NotificationCompat.Builder`, and displays it using `NotificationManagerCompat`.

Thus, the objective of developing an Android application for displaying notifications was successfully achieved.

---

# Student Information

**Name:** Tejas Sunil Waske

**USN:** 25MCAR0189

**Experiment:** Experiment 5 – Displaying Notifications in Android

---

# GitHub Repository

**Repository Name:** NotificationDemoMAD5

**GitHub Link:**

https://github.com/twaske2-dotcom/NotificationDemoMAD5

---

# Reference

- Android Developers – Notifications
- Android Developers – Notification Channels
- Android Developers – Notification Runtime Permission

---

## Author

**Tejas Sunil Waske**

**USN:** 25MCAR0189
