<!-- 
# Interview Questions

## 1. What is an android?
- Android is an open-source mobile operating system developed by Google. It is based on the Linux kernel and designed for touchscreen devices like smartphones, tablets, smart TVs, and wearables. It provides a rich user interface, supports multiple programming languages (Java/Kotlin), and allows developers to create and distribute applications via the Google Play Store.

### Key Features:
- Open-source and customizable
- Supports Java and Kotlin for development
- Uses XML for UI design
- Provides an integrated development environment - (Android Studio)
- Offers built-in security, notifications, and background processing


## 2. What is SDK?
- The Android Software Development Kit (SDK) is a collection of tools, libraries, and documentation required to develop, test, and debug Android applications.

### Key Components of SDK:
- SDK Tools – Includes debugging, testing, and - emulator tools.
- Android Emulator – Simulates Android devices on a - computer.
- SDK Platform Tools – Includes ADB (Android Debug - Bridge) for managing devices.
- Build Tools – Converts source code into APK files.
- Android Libraries – Predefined libraries for UI, networking, and storage.


## 3. What are local databases
- A local database in Android is a database stored on the device, allowing apps to store and retrieve data even without an internet connection.

### Common Local Databases in Android:
- SQLite – A lightweight relational database built - into Android.
- Room Database – A wrapper over SQLite that - simplifies database operations.
- SharedPreferences – Used for storing small - key-value data.
- Realm Database – A mobile database designed for high performance.


## 4. Query of crud
- CRUD operations refer to the four basic database operations:

- Create (Insert) – Adds new records to the database.
- Read (Select) – Retrieves records from the database.
- Update – Modifies existing records.
- Delete – Removes records from the database.


## 5. what is the lifecycle of Android
## 6. what are manifest files?
## 7. What is service
## 8. types of intent
## 9. what is API?
## 10. How to call API? -->


<!-- --------------------- -->

# Android Development Interview Questions & Answers

## 📌 1. What is Android?
**Android** is an open-source **mobile operating system** developed by Google, primarily designed for touchscreen devices.

## 📌 2. What are the features of Android?
✔ Open-source  
✔ Linux-based  
✔ Supports multiple screen sizes  
✔ Multi-tasking  
✔ Google Play Store support  

## 📌 3. What is the latest version of Android?
You can check the latest version [here](https://developer.android.com/about/versions/)

## 📌 4. What is an APK file?
**APK (Android Package Kit)** is the package file format for Android applications.

## 📌 5. What is the difference between an APK and an AAB file?
| Feature  | APK  | AAB  |
|----------|------|------|
| File Size | Larger | Smaller |
| App Distribution | Direct Installation | Google Play Store |
| Splitting | No | Yes (Dynamic Delivery) |

## 📌 6. What is the Android Architecture?
1. **Linux Kernel**  
2. **Hardware Abstraction Layer (HAL)**  
3. **Android Runtime (ART)**  
4. **Application Framework**  
5. **Applications**

## 📌 7. What is the use of Linux Kernel in Android?
✔ Memory & Power Management  
✔ Drivers (Wi-Fi, Bluetooth, Camera)  
✔ Security (SELinux)  

## 📌 8. What are the key components of Android?
✔ Activities  
✔ Services  
✔ Broadcast Receivers  
✔ Content Providers  

## 📌 9. What is Dalvik Virtual Machine (DVM)?
Dalvik is a virtual machine used in older Android versions to execute bytecode.

## 📌 10. What is ART (Android Runtime)?
**ART** replaces Dalvik, improving performance using **Ahead-of-Time (AOT) compilation**.

## 📌 11. What is the role of Gradle in Android development?
Gradle is a **build automation tool** that manages dependencies and builds the APK.

## 📌 12. What is an Activity in Android?
An **Activity** represents a single screen with UI components.

```java
public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }
}
```

## 📌 13. What is an Intent in Android?
An **Intent** is a messaging object used to communicate between components.

### 📌 14. Types of Intents
1. **Explicit Intent** (Targeted Component)
2. **Implicit Intent** (No Specific Component)

### 📌 15. Example of Explicit Intent
```java
Intent intent = new Intent(this, SecondActivity.class);
startActivity(intent);
```

### 📌 16. Example of Implicit Intent
```java
Intent intent = new Intent(Intent.ACTION_VIEW, Uri.parse("https://google.com"));
startActivity(intent);
```

## 📌 17. What is the role of the AndroidManifest.xml file?
✔ Declares app permissions  
✔ Registers activities & services  
✔ Defines hardware & software requirements  

## 📌 18. What is a Context in Android?
A **Context** provides access to system resources like databases, shared preferences, etc.

## 📌 19. What is the difference between getContext(), getApplicationContext(), and this in Android?
| Method | Scope |
|--------|-------|
| getContext() | Fragment Context |
| getApplicationContext() | Application-wide Context |
| this | Activity Context |

## 📌 20. What is an AIDL in Android?
**AIDL (Android Interface Definition Language)** allows IPC (Inter-Process Communication).

## 📌 21. What is an Activity Lifecycle in Android?

| Lifecycle Method | Purpose |
|-----------------|---------|
| onCreate() | Initialize activity |
| onStart() | Activity visible to user |
| onResume() | Activity comes to foreground |
| onPause() | Activity goes into the background |
| onStop() | Activity no longer visible |
| onDestroy() | Activity destroyed |

## 📌 22. What is a RecyclerView in Android?
A **RecyclerView** is an advanced **ListView** that efficiently displays large datasets.

### Example:
```java
RecyclerView recyclerView = findViewById(R.id.recyclerView);
recyclerView.setLayoutManager(new LinearLayoutManager(this));
```

## 📌 23. How to handle click events in RecyclerView?
```java
holder.itemView.setOnClickListener(v -> {
    Toast.makeText(context, "Item Clicked", Toast.LENGTH_SHORT).show();
});
```

## 📌 24. What are the different storage options in Android?
✔ SharedPreferences (Key-Value Store)  
✔ Internal Storage  
✔ External Storage  
✔ SQLite Database  
✔ Room Database  

## 📌 25. What is Retrofit in Android?
**Retrofit** is a networking library for API calls.

```java
@GET("users/{id}")
Call<User> getUser(@Path("id") int userId);
```

## 📌 26. What is LiveData in Android?
**LiveData** is an observable data holder used in ViewModel.

```java
MutableLiveData<String> name = new MutableLiveData<>();
```

## 📌 27. What is Firebase Cloud Messaging (FCM)?
**FCM** is used to send push notifications.

## 📌 28. What is a ViewModel in Android?
**ViewModel** manages UI-related data in a lifecycle-aware manner.

## 📌 29. What is WorkManager in Android?
**WorkManager** is used to schedule background tasks efficiently.

## 📌 30. How to handle push notifications in Android?
```java
FirebaseMessaging.getInstance().subscribeToTopic("news");
```

---
### 📌 **Summary**
| Concept | Key Points |
|---------|-----------|
| **Activity** | Single screen UI |
| **RecyclerView** | Efficient list rendering |
| **ViewModel** | UI data management |
| **LiveData** | Observable data changes |
| **Retrofit** | API calls |
| **FCM** | Push notifications |
| **Room** | SQLite ORM |
| **WorkManager** | Background task scheduling |

---
### 📌 **📢 Need More Help?**
📧 Feel free to reach out! 🚀
