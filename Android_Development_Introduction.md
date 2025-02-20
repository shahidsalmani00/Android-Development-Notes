# Introduction to Android Development

## What is Android Development?

Android Development is the process of creating applications for Android devices using programming languages like Java or Kotlin with XML for UI design. It involves designing user interfaces, handling user interactions, managing data, and ensuring smooth performance. Applications run on the Android operating system, which is based on a modified Linux kernel. Developers use Android Studio, the official IDE, to build, test, and deploy Android apps.


## Overview of Android Development

Android development involves creating mobile applications that interact with users through different UI elements. It follows the <b>Model-View-Controller (MVC)</b> architecture and uses various components such as <b>Activities, Fragments, Services, Broadcast Receivers, and Content Providers</b> to build robust applications.

### Key Highlights:
    Languages Used: Java and Kotlin.
    UI Design: XML for layouts.
    IDE: Android Studio.
    App Components: Activities, Fragments, Services, etc.
    Development Framework: Android SDK.


## 1. System Requirements for Android Studio
Before installing Android Studio, ensure your system meets the following minimum requirements :

### For Windows:
- OS: Windows 10 or later (64-bit)
- RAM: At least 8 GB (16 GB recommended)
- Disk Space: Minimum 8 GB of free space (SSD recommended)
- Processor: Intel Core i3 or equivalent (Core i5/i7 - recommended)
- JDK (Java Development Kit): Included in Android Studio
    
### For macOS:
- OS: macOS 10.14 (Mojave) or later
- RAM: At least 8 GB (16 GB recommended)
- Disk Space: Minimum 8 GB of free space
- Processor: Apple M1/M2 or Intel Core i5/i7

## 2. Steps to Install Android Studio
### Step 1: Download Android Studio
- Visit the official [Android Studio download page](https://- developer.android.com/studio).
- Select the appropriate version for Windows, macOS, or Linux.
- Click Download and agree to the terms and conditions.
- Step 2: Install Android Studio

### For Windows:
- Run the downloaded .exe file.<br>
- Select Standard Installation and click Next.<br>
- Choose the installation location and click Install.<br>
- Once installed, launch Android Studio.<br>

### For macOS:
- Open the downloaded .dmg file.
- Drag Android Studio into the Applications folder.
- Open Android Studio and follow the setup wizard.

## 3. First-time Setup and Configuration
- After installation, Android Studio will guide you through an initial setup wizard.

### Step 1: Install Required Components
- Select Standard Setup (recommended).
Android Studio will download necessary SDK components.

### Step 2: Configure the Android Emulator
- Install the Android Emulator for testing apps.
Select a device profile (e.g., Pixel 6) and download the 
system image.

### Step 3: Verify Installation
- Open Android Studio and create a new project to ensure everything works correctly.

## Key Components of Android Development
### Android Studio
- Android Studio is the official Integrated Development Environment (IDE) for Android development. It provides tools for writing, debugging, and testing Android applications.

### Android SDK (Software Development Kit)
- The Android SDK includes essential libraries, APIs, and tools that allow developers to build Android applications efficiently. It includes emulator support, debugging tools, and frameworks for development.

### XML for UI Design
- XML (Extensible Markup Language) is used to design the user interface of Android applications. It defines layouts, views, and UI elements in a structured manner.

### Java/Kotlin for Backend Logic
- Java and Kotlin are the primary programming languages used in Android development. They handle user interactions, data processing, and application logic.

### Android Manifest File
- The AndroidManifest.xml file contains essential information about the app, including its components (activities, services, broadcast receivers), permissions, and application metadata.

## Running a Simple App to Test Installation
- After installing Android Studio, create a simple <b>Hello World</b> application.

### XML Layout (activity_main.xml)
```XML
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical">

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hello, World!"
        android:textSize="24sp"/>
</LinearLayout>
```

### Java Code (MainActivity.java)
```Java
package com.example.helloworld;

import android.os.Bundle;
import android.widget.TextView;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Set text programmatically
        TextView textView = findViewById(R.id.textView);
        textView.setText("Hello, Android with Java!");
    }
}
```

### Kotlin Code (MainActivity.kt)
```Kotlin
package com.example.helloworld

import android.os.Bundle
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        // Set text programmatically
        val textView: TextView = findViewById(R.id.textView)
        textView.text = "Hello, Android with Kotlin!"
    }
}
```



