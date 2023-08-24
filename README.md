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
### Intent & Intent Filter
```
val intent = new Intent(Intent.ACTION_VIEW) -> Implicit Intent (doesn't specify the action)
intent.setData(Uri.parse("http://www.javatpoint.com"))
startActivity(intent)

val intent = new Intent(this, MainActivity:class.java) -> Explicit Intent (where we pass component or external class)
startActivity(intent)

<intent-filter -> The intent filter specifies the types of intents that an activity, service, or broadcast receiver can respond.
android:icon="drawable resource"
android:label="string resource"
android:priority="integer" >
. . .
</intent-filter>
```
### Views In Android
```
Text View -> This class is used to display text on the android application screen. It also
allows user to optionally edit it.
Edit Text -> This class makes text to be editable in Android application. It helps in
building the data interface taken from any user.
Image view -> Image view helps to display images in an android application. Any image can be
selected, we just have to paste our image in a drawable folder from where we can access it. 
Check Box -> Checkbox is used in that applications where we have to select one option from
multiple provided. 
Radio Button -> Radio button is like checkbox, but there is slight difference between them.
Radio button is a  two-states button that can be either checked or unchecked.
Button View -> This class is used to create a button on an application screen. Buttons are
very helpful in getting into a content. Android button represents a clickable push-button
widget.
Image Button View -> Image button is a button but it carries an image on it. We can put an
image or a certain text on it and when we click it provides the operations assigned to it.
```
### ViewGroups In Android
```
LinearLayout is a view group that aligns all children in a single direction, vertically or
horizontally. You can specify the layout direction with the android:orientation attribute.

RelativeLayout is a view group that displays child views in relative positions. The position
of each view can be specified as relative to sibling elements (such as to the left-of or
below another view) or in positions relative to the parent RelativeLayout area (such as
aligned to the bottom, left or center) using IDs.

Frame Layout is designed to block out an area on the screen to display a single item. Mostly
used in fragments.

Constraint Layout is used to define a layout by assigning constraints for every child
view/widget relative to other views present. A ConstraintLayout is similar to a
RelativeLayout, but with more power.
```
### Recycler View
```
RecyclerView makes it easy to efficiently display large sets of data. You supply the data and
define how each item looks, and the RecyclerView library dynamically creates the elements
when they're needed.

RecyclerView is the ViewGroup that contains the views corresponding to your data. It's a view
itself, so you add RecyclerView to your layout the way you would add any other UI element.

Each individual element in the list is defined by a view holder object. When the view holder
is created, it doesn't have any data associated with it. After the view holder is created,
the RecyclerView binds it to its data. You define the view holder by extending
RecyclerView.ViewHolder.

The RecyclerView requests views, and binds the views to their data, by calling methods in the
adapter. You define the adapter by extending RecyclerView.Adapter.

The layout manager arranges the individual elements in your list. You can use one of the
layout managers provided by the RecyclerView library, or you can define your own. Layout
managers are all based on the library's LayoutManager abstract class.

class CustomAdapter(private val dataSet: Array<String>) :
        RecyclerView.Adapter<CustomAdapter.ViewHolder>() {

    /**
     * Provide a reference to the type of views that you are using
     * (custom ViewHolder)
     */
    class ViewHolder(view: View) : RecyclerView.ViewHolder(view) {
        val textView: TextView

        init {
            // Define click listener for the ViewHolder's View
            textView = view.findViewById(R.id.textView)
        }
    }

    // Create new views (invoked by the layout manager)
    override fun onCreateViewHolder(viewGroup: ViewGroup, viewType: Int): ViewHolder {
        // Create a new view, which defines the UI of the list item
        val view = LayoutInflater.from(viewGroup.context)
                .inflate(R.layout.text_row_item, viewGroup, false)

        return ViewHolder(view)
    }

    // Replace the contents of a view (invoked by the layout manager)
    override fun onBindViewHolder(viewHolder: ViewHolder, position: Int) {

        // Get element from your dataset at this position and replace the
        // contents of the view with that element
        viewHolder.textView.text = dataSet[position]
    }

    // Return the size of your dataset (invoked by the layout manager)
    override fun getItemCount() = dataSet.size

}
```
### ViewPager
```
Android ViewPager widget is found in the support library and it allows the user to swipe left
or right to see an entirely new screen. Today we’re implementing a ViewPager by using Views
and PagerAdapter.

<android.support.v4.view.ViewPager
        android:id="@+id/viewpager"
        android:layout_width="match_parent"
        android:layout_height="match_parent"/>

ViewPager viewPager = (ViewPager) findViewById(R.id.viewpager);
viewPager.setAdapter(new CustomPagerAdapter(this));

package com.journaldev.viewpager;
public enum ModelObject {
    RED(R.string.red, R.layout.view_red),
    BLUE(R.string.blue, R.layout.view_blue),
    GREEN(R.string.green, R.layout.view_green);

    private int mTitleResId;
    private int mLayoutResId;

    ModelObject(int titleResId, int layoutResId) {
        mTitleResId = titleResId;
        mLayoutResId = layoutResId;
    }

    public int getTitleResId() {
        return mTitleResId;
    }

    public int getLayoutResId() {
        return mLayoutResId;
    }
}
```
### Spinner
```
Spinners provide a quick way to select one value from a set. In the default state, a spinner shows its currently selected value. Touching the spinner displays a dropdown menu with all other available values, from which the user can select a new one.

<Spinner
    android:id="@+id/planets_spinner"
    android:layout_width="match_parent"
    android:layout_height="wrap_content" />

<?xml version="1.0" encoding="utf-8"?>
<resources>
    <string-array name="planets_array">
        <item>Mercury</item>
        <item>Venus</item>
        <item>Earth</item>
        <item>Mars</item>
        <item>Jupiter</item>
        <item>Saturn</item>
        <item>Uranus</item>
        <item>Neptune</item>
    </string-array>
</resources>

val spinner: Spinner = findViewById(R.id.spinner)
// Create an ArrayAdapter using the string array and a default spinner layout
ArrayAdapter.createFromResource(
        this,
        R.array.planets_array,
        android.R.layout.simple_spinner_item
).also { adapter ->
    // Specify the layout to use when the list of choices appears
    adapter.setDropDownViewResource(android.R.layout.simple_spinner_dropdown_item)
    // Apply the adapter to the spinner
    spinner.adapter = adapter
}

class SpinnerActivity : Activity(), AdapterView.OnItemSelectedListener {

    override fun onItemSelected(parent: AdapterView<*>, view: View?, pos: Int, id: Long) {
        // An item was selected. You can retrieve the selected item using
        // parent.getItemAtPosition(pos)
    }

    override fun onNothingSelected(parent: AdapterView<*>) {
        // Another interface callback
    }
}

val spinner: Spinner = findViewById(R.id.spinner)
spinner.onItemSelectedListener = this
```
<!--
* CustomView
   * Canvas
   * Bitmap
   * Paint
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
