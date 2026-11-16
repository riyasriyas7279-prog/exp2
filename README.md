# Experiment 2: Android Activity Lifecycle

## Objective
To understand and implement the various lifecycle methods of an Android Activity and observe their execution flow through logging and user interface feedback.

## Student Details
- **Name:** Santhosh Kumar.S
- **Register Number:** 25MCAR0133

## Introduction
The Android Activity Lifecycle is a set of states an activity can be in, from when it is first created until it is destroyed. As an activity transitions between these states, the Android system calls lifecycle callback methods where you can run code to manage resources and UI state.

## Lifecycle Methods Implemented

| Method | Description |
| :--- | :--- |
| `onCreate()` | Called when the activity is first created. This is where you perform basic application startup logic that should happen only once for the entire life of the activity. |
| `onStart()` | Called when the activity becomes visible to the user, as the app prepares for the activity to enter the foreground and become interactive. |
| `onResume()` | Called when the activity will start interacting with the user. At this point your activity is at the top of the activity stack, with user input going to it. |
| `onPause()` | Called when the system is about to start resuming a previous activity. This is typically used to commit unsaved changes to persistent data, stop animations and other things that may be consuming CPU. |
| `onStop()` | Called when the activity is no longer visible to the user, because another activity has been resumed and is covering this one. |
| `onRestart()` | Called after your activity has been stopped, prior to it being started again. |
| `onDestroy()` | The final call you receive before your activity is destroyed. This can happen either because the activity is finishing, or because the system is temporarily destroying this instance to save space. |

## Implementation Details
In this experiment, each lifecycle method in `MainActivity.kt` has been overridden to include:
1. **Logcat Messaging:** Using `Log.d("LifecycleDemo", "...")` to print method calls to the Android Studio console.
2. **Toast Notifications:** Using `Toast.makeText(...)` to display a short visual message on the device screen for each transition.

## How to Verify
1. **Build and Run:** Run the application on an Android Emulator or Physical Device.
2. **Open Logcat:** In Android Studio, open the **Logcat** window and filter by the tag `LifecycleDemo`.
3. **Interact with the App:**
    - **Launch App:** Observe `onCreate` -> `onStart` -> `onResume`.
    - **Press Home:** Observe `onPause` -> `onStop`.
    - **Return to App:** Observe `onRestart` -> `onStart` -> `onResume`.
    - **Press Back:** Observe `onPause` -> `onStop` -> `onDestroy`.

## Screenshots

### Screenshot 1
![Screenshot 1](./Screenshot%202026-08-08%20200119.png)

*Description: Main activity launched showing lifecycle toast/log output.*

### Screenshot 2
![Screenshot 2](./Screenshot%202026-08-08%20200146.png)

*Description: App after navigating or performing an action demonstrating another lifecycle transition.*

---
*Developed as part of the Mobile Application Development (MAD) Lab.*
