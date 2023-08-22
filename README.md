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
### build.gradle (Module:App)
```
android {
    compileSdkVersion 29 -> sdk on which your app gets compiled
    buildToolsVersion "29.0.3" -> version you want to use to build tools

    defaultConfig {
        applicationId "com.example.myapp" -> package name
        minSdkVersion 15 -> minimum sdk which can run your app
        targetSdkVersion 29 -> targeted sdk device for your app
        versionCode 1 -> version of your app
        versionName "1.0" -> formal name of version

        testInstrumentationRunner "androidx.test.runner.AndroidJUnitRunner" -> for testing and running your app
    }

    buildTypes {
        release {
            minifyEnabled false
            proguardFiles getDefaultProguardFile('proguard-android-optimize.txt'), 'proguard-rules.pro'
        }
    }
}

dependencies { -> list of all dependencies are added here
    implementation fileTree(dir: 'libs', include: ['*.jar'])
    implementation 'androidx.appcompat:appcompat:1.1.0'
    implementation 'androidx.constraintlayout:constraintlayout:1.1.3'
    testImplementation 'junit:junit:4.12'
    androidTestImplementation 'androidx.test.ext:junit:1.1.1'
    androidTestImplementation 'androidx.test.espresso:espresso-core:3.2.0'
}
```
### build.gradle (Project:App)
```
buildscript {
    repositories {
        google()
        jcenter()
    }
    dependencies {
        classpath 'com.android.application'
    }
}

allprojects {
    repositories {
        google()
        jcenter()
    }
}

task clean(type: Delete) {
    delete rootProject.buildDir
}
```
### gradle.properties (Gradle Properties)
```
org.gradle.jvmargs=-Xmx1536m -> Specify the version of the Gradle build tools to use
myCustomProperty=foo -> custom property for build
```
[More about .gradle files](https://blog.devgenius.io/what-is-the-gradle-scripts-folder-in-an-android-project-c4b019ea95e0#:~:text=gradle%20file%20is%20located%20in,the%20app%2C%20and%20other%20settings.)
### Activity LifeCycle
```
onCreate() -> This is the first callback and called when the activity is first created.
onStart() -> This callback is called when the activity becomes visible to the user.
onResume() -> This is called when the user starts interacting with the application.
onPause() -> The paused activity does not receive user input and cannot execute any code and called when
the current activity is being paused and the previous activity is being resumed.
onStop() -> This callback is called when the activity is no longer visible.
onDestroy() -> This callback is called before the activity is destroyed by the system.
onRestart() -> This callback is called when the activity restarts after stopping it.
```
### Activity BackStack 
```
BackStack is a stack where a activity or a task get pushed when you call a new acitivity and when you click back
it comes back to the last used activity.
```
### Android Components -> Activity
```
An activity represents a single screen with a user interface, in-short Activity performs actions on the screen.
For example, an email application might have one activity that shows a list of new emails, another activity to
compose an email, and another activity for reading emails. If an application has more than one activity, then one
of them should be marked as the activity that is presented when the application is launched.

public class MainActivity extends Activity {
}
```
### Android Components -> Service
```
A service is a component that runs in the background to perform long-running operations. For example, a service might
play music in the background while the user is in a different application, or it might fetch data over the network
without blocking user interaction with an activity.

public class MyService extends Service {
}
```
### Android Components -> Broadcast Recievers
```
Broadcast Receivers simply respond to broadcast messages from other applications or from the system. For example,
applications can also initiate broadcasts to let other applications know that some data has been downloaded to the
device and is available for them to use, so this is broadcast receiver who will intercept this communication and will initiate
appropriate action.

public class MyReceiver  extends  BroadcastReceiver {
   public void onReceive(context,intent){}
}
```
### Android Components -> Content Provider
```
A content provider component supplies data from one application to others on request. Such requests are handled by
the methods of the ContentResolver class. The data may be stored in the file system, the database or somewhere
else entirely. A content provider is implemented as a subclass of ContentProvider class and must implement a standard
set of APIs that enable other applications to
perform transactions.

public class MyContentProvider extends  ContentProvider {
   public void onCreate(){}
}
```
<!--
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
