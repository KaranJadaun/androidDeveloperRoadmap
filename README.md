# Android Developer Roadmap By [Amit Shekhar](https://github.com/amitshekhariitbhu/android-developer-roadmap)

### Kotlin Basic
```
fun main() {
  print("Hello")
  var k = 29 -> mutable
  val j = 20 -> inmutable
  print("my number is $k") -> directly print value in print statement
}
```
```
if (x > y) {
  ...
} else if {
  ...
} else {
  ...
}
```
```
val arr = arrayOf(1,2,3,4,5)
val list = mutableListOf<Int>(1,2,3,4,5)
while (x > 10) {
  ...
}
for (num in arr) {
  ...
}
for (i in 0..arr.size - 1) {
  ...
}
```
### Kotlin Error and Exception
```
var a = 10
var b = 0
try {
  var ans = a/b
  print("done")
} catch (e : DivideByZero) {
  print("change values")
} finally {
  print("program done")
}
```
### Kotlin Null Pointer
```
val value : String? = null -> use ? for null safety
print(value?.length) -> use ? everywhere where the value is used
```
### Kotlin Classes/Objects
```
class Dog {
  var breed: String = "Labrador"
  var color: String = "Brown"
  var age: Int = 3
  fun eat() {
    print("eat")
  }
  fun bark() {
    print("talk")
  }
}
```
### Kotlin Constructor
```
class Dog(var breed: String, var color: String, var age: Int) {
  fun eat() {}
  fun bark() {}
}
```
### Kotlin Inheritance & Interface
```
open class Animals(var legs: Int, var color: String) {
  fun eat() = print("eat")
  fun sleep() = print("sleep")
}
class Dogs(legs: Int, color: String): Animals(legs, color) {
  fun bark() = print("bark")
}
class Cats(legs: Int, color: String): Animals(legs, color) {
  fun meow() = print("meow")
}
class Hello: MyInterface, NewInterface {} -> for hybrid inheritance
```
### Override And Modefiers
```
In Animal Class -> open fun sounds() = print("yes")
In Dogs Class > override fun sounds() = print("bark")

public class -> open for all, default
internal class -> only for modules
private class -> only for class
protected class -> not visible even in class
```
<!--
* Android Studio
   * Android Studio IDE Overview
   * Project Structure
   	   * Java/Kotlin
   	   * XML
   	   * .gradle files
* Android Component
   * Activity
     * Activity Lifecycle
     * Tasks & Back Stack
   * Service
   * Broadcast Receiver
   * Content Provider
* Intents
   * Types of Intent
     * Implicit
     * Explicit
   * Intent Filter
* Static User Interface
  * View
      * Button, ImageView, TextView, EditText etc
  * ViewGroup
  	   * LinearLayout, RelativeLayout, FrameLayout, ConstraintLayout
* Dynamic User Interface
   * RecyclerView
   * ViewPager
   * Spinner
* CustomView
   * Canvas
   * Bitmap
   * Paint
* UI Resources
   * Drawables
   * String
   * Styles
* Fragments
   * Fragment Lifecycle
   * Fragment Manager
* Support User Interface
  * ProgressBar
  * Dialogs
  * Toast & Snackbar
* Storage
  * Shared Preferences
  * File Systems
  * Database
    * RoomDB
* Build
  * Gradle
  * Debug / Release Configuration
* Threading 
  * Thread
  * Handler/Looper
  * ThreadPoolExecutor
  * RxJava
  * Coroutines/Flow
  * WorkManager
* Debugging
  * Memory profiling
  * Logging
  * Systrace
  * Exceptions
  * Error Handling
* Memory Leak
  * Detecting and Fixing Memory Leaks
  * Context
* 3rd Party Library
  * Image Loading
     * Glide
     * Picasso
  * Dependency Injection
     * Dagger
  * Networking
     * Fast Android Networking Library
     * Retrofit
  * MultiThreading
     * RxJava
     * Coroutines
     * Kotlin Flow API
* Coroutines - You can learn these topics here:
  * coroutines
  * suspend
  * launch, async-await, withContext
  * dispatchers
  * scope, context, job
  * lifecycleScope, viewModelScope, GlobalScope
  * suspendCoroutine, suspendCancellableCoroutine
  * coroutineScope, supervisorScope
* Kotlin Flow API - You can learn these topics here: 
  * Flow Builder, Operator, Collector
  * flowOn, dispatchers
  * Operators such as filter, map, zip, flatMapConcat, retry, debounce, distinctUntilChanged, flatMapLatest
  * Terminal operators
  * Cold Flow vs Hot Flow:
  * [StateFlow, SharedFlow], callbackFlow, channelFlow
* Data Format
  * JSON
     * GSON
  * Flat Buffer
  * Protocol Buffer
* Networking
  * GET/POST/DELETE/PUT/PATCH
  * OkHttp, Interceptor
  * Caching
  * Retrofit with Coroutines/Flow
  * Multipart request
  * Read, Write Timeout
  * OAuth 2.0 - Refresh and Access Token
  * HTTP Status Codes
* Android Jetpack
  * Foundation Components
     * AppCompat
     * Android KTX
     * Multidex
  * Architecture Components
     * LiveData
     * ViewModel
     * DataBinding
     * Paging
     * Work Manager
     * Navigation
  * Behaviour Components 
     * Download Manager
     * Media Playback
     * Notification
     * Permissions
     * Preference
     * Sharing
     * Slice
  * UI Component
     * Animation & Transition
     * Android Auto
     * Emoji
     * Palette
     * Android TV
     * Android Wear
* Compose
     * State: remember, rememberSaveable, MutableState
     * Recomposition
     * State hoisting
     * Side-effects
     * Modifier
     * Theme
     * Layout, List
     * Gestures, Animation
     * CompositionLocal
* Common Design Patterns and Architecture 
     * Builder Pattern
     * Singleton
     * Dependency Injection
     * Factory
     * Observer
     * Repository
     * MVVM
     * MVP
     * MVI
     * Clean architecture
* Unit Testing
  	 * Local Unit Testing
  	 * Instrumentation Testing
* Firebase
     * FCM
     * Crashlytics
     * Analytics
     * Remote Config
     * App Indexing
     * Dynamic Link
* Security
     * Encrypt / Decrypt
     * Proguard
     * R8
* App Release
     * .keystore file
     * App Bundle
     * Playstore
* Keep Learning and Improving
-->
