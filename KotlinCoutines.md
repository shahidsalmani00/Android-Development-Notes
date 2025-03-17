

## 🌟 What are Kotlin Coroutines?

Kotlin Coroutines are a way to write **asynchronous and non-blocking code** in a **sequential and readable manner**. Coroutines help manage background tasks like **network calls**, **database operations**, etc., **without blocking the main thread (UI thread)**.

Think of coroutines like lightweight threads – but **much cheaper and more efficient** than Java threads.

---

## 🧠 Why use Coroutines?

- Easy to manage **long-running tasks** like network requests or file I/O.
- Avoid **callback hell**.
- Improve **code readability**.
- **Suspend and resume** execution efficiently.

---

## ⚙️ Core Concepts of Coroutines

| Term             | Description                                              |
| ---------------- | -------------------------------------------------------- |
| CoroutineScope   | Defines the **lifecycle** of a coroutine.                |
| Dispatcher       | Decides **which thread** the coroutine runs on.          |
| Job              | Represents a coroutine task. Can be cancelled.           |
| suspend function | Pauses coroutine execution without blocking the thread.  |
| launch {}        | Starts a coroutine that **does not return a result**.    |
| async {}         | Starts a coroutine that **returns a result** (Deferred). |

---

## 📌 Coroutine Builders (Methods to create coroutines):

| Method         | Description                                                   |
| -------------- | ------------------------------------------------------------- |
| launch {}      | Fire and forget. Used when you don’t need a result.           |
| async {}       | Used when you want a result (like a background calculation).  |
| runBlocking {} | Blocks the current thread, usually used in `main()` or tests. |

---

## 💡 Types of Coroutine Dispatchers

| Dispatcher             | Description                                  |
| ---------------------- | -------------------------------------------- |
| Dispatchers.Main       | Runs on **main/UI thread** (for UI updates). |
| Dispatchers.IO         | For **network/database** operations.         |
| Dispatchers.Default    | For **CPU-intensive tasks** (e.g., sorting). |
| Dispatchers.Unconfined | Runs on current thread until suspension.     |

---

## ✅ Example 1: Basic Coroutine with `launch`

```kotlin
import kotlinx.coroutines.*

fun main() = runBlocking {
    println("Main Start: ${Thread.currentThread().name}")

    launch {
        delay(1000) // suspend for 1 sec
        println("Coroutine: ${Thread.currentThread().name}")
    }

    println("Main End: ${Thread.currentThread().name}")
}
```

### 📌 Output:

```
Main Start: main
Main End: main
Coroutine: main
```

---

## ✅ Example 2: Coroutine with Dispatcher

```kotlin
import kotlinx.coroutines.*

fun main() = runBlocking {
    launch(Dispatchers.IO) {
        println("Running in IO: ${Thread.currentThread().name}")
    }

    launch(Dispatchers.Default) {
        println("Running in Default: ${Thread.currentThread().name}")
    }
}
```

---

## ✅ Example 3: `async` and `await`

```kotlin
import kotlinx.coroutines.*

fun main() = runBlocking {
    val result = async {
        delay(1000)
        return@async 10 + 20
    }

    println("The result is: ${result.await()}")
}
```

---

## ✅ Example 4: `suspend` Function

```kotlin
import kotlinx.coroutines.*

suspend fun fetchData(): String {
    delay(1000) // Simulate API call
    return "Data from Server"
}

fun main() = runBlocking {
    val data = fetchData()
    println("Received: $data")
}
```

---

## ✅ Example 5: CoroutineScope in Android (Real-life example)

```kotlin
class MainActivity : AppCompatActivity() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        // Coroutine inside lifecycle scope
        lifecycleScope.launch(Dispatchers.IO) {
            val data = fetchData()
            withContext(Dispatchers.Main) {
                // Update UI here
                textView.text = data
            }
        }
    }

    suspend fun fetchData(): String {
        delay(2000)
        return "Hello from Server"
    }
}
```

---

## 📚 Summary:

| Concept        | Description                |
| -------------- | -------------------------- |
| CoroutineScope | Where the coroutine lives. |
| suspend        | Suspends without blocking. |
| launch         | Fire and forget.           |
| async/await    | Get result from coroutine. |
| Dispatcher     | Thread control.            |

---

## 📂 Contribution

Feel free to fork this repository and contribute more coroutine examples like:
- Retrofit + Coroutines
- Room Database Integration
- Coroutine Exception Handling

Pull Requests are welcome ✅

---

