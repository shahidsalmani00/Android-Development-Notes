# Firebase Realtime Database Example - Android App with Kotlin

## 🔥 What is Firebase Realtime Database?
Firebase Realtime Database is a **cloud-hosted NoSQL database** that stores data in **JSON format** and syncs data in **real time** across all clients.

---

## ✨ Features:
- Real-time syncing
- Offline support
- JSON Tree Structure

---

## ⚙️ Setup Firebase in Android

### a. Add Firebase Project:
1. Create Project on Firebase Console
2. Add Android App
3. Download `google-services.json` → put in `app/`

### b. Add Dependencies:
**Project level:**
```gradle
classpath 'com.google.gms:google-services:4.4.0'
```
**App level:**
```gradle
plugins {
    id 'com.android.application'
    id 'com.google.gms.google-services'
}
dependencies {
    implementation 'com.google.firebase:firebase-database-ktx'
}
```

---

## 🏗️ Create Data Model
```kotlin
data class User(
    var name: String = "",
    var age: Int = 0
)
```

---

## 📱 Layout (activity_main.xml)
```xml
<LinearLayout ... >
    <EditText android:id="@+id/etName" ... />
    <EditText android:id="@+id/etAge" ... />
    <Button android:id="@+id/btnSave" ... />
    <TextView android:text="User List:" ... />
    <ListView android:id="@+id/userListView" ... />
</LinearLayout>
```

---

## 🔧 MainActivity.kt
```kotlin
class MainActivity : AppCompatActivity() {

    private lateinit var etName: EditText
    private lateinit var etAge: EditText
    private lateinit var btnSave: Button
    private lateinit var userListView: ListView

    private lateinit var databaseRef: DatabaseReference
    private val userList = ArrayList<String>()
    private lateinit var adapter: ArrayAdapter<String>

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        etName = findViewById(R.id.etName)
        etAge = findViewById(R.id.etAge)
        btnSave = findViewById(R.id.btnSave)
        userListView = findViewById(R.id.userListView)

        databaseRef = FirebaseDatabase.getInstance().getReference("Users")

        adapter = ArrayAdapter(this, android.R.layout.simple_list_item_1, userList)
        userListView.adapter = adapter

        btnSave.setOnClickListener { saveUser() }

        getUsersFromFirebase()
    }

    private fun saveUser() {
        val name = etName.text.toString()
        val age = etAge.text.toString().toIntOrNull()

        if (name.isNotEmpty() && age != null) {
            val userId = databaseRef.push().key!!
            val user = User(name, age)
            databaseRef.child(userId).setValue(user)
        }
    }

    private fun getUsersFromFirebase() {
        databaseRef.addValueEventListener(object : ValueEventListener {
            override fun onDataChange(snapshot: DataSnapshot) {
                userList.clear()
                for (userSnap in snapshot.children) {
                    val user = userSnap.getValue(User::class.java)
                    user?.let { userList.add("${it.name}, Age: ${it.age}") }
                }
                adapter.notifyDataSetChanged()
            }

            override fun onCancelled(error: DatabaseError) {
                Toast.makeText(this@MainActivity, error.message, Toast.LENGTH_SHORT).show()
            }
        })
    }
}
```

---

## 🔐 Firebase Rules for Testing
```json
{
  "rules": {
    ".read": true,
    ".write": true
  }
}
```

---

## 📚 Summary Checklist
- [x] Firebase setup done
- [x] Realtime Database configured
- [x] Model created
- [x] Data saved and retrieved
- [x] UI connected to database

---

Let me know if you want me to include screenshots, advanced CRUD operations, or login authentication using Firebase Auth.

