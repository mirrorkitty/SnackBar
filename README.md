DEPRECATED
=========
With the addition of Snackbars to the [android design support library](http://developer.android.com/tools/support-library/features.html#design) this library is no longer under development.



SnackBar
========
[![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-Kennyc1012%2FSnackBar-brightgreen.svg?style=flat)](https://android-arsenal.com/details/1/997)
[![API](https://img.shields.io/badge/API-11%2B-brightgreen.svg?style=flat)](https://android-arsenal.com/api?level=11)

#Designed after the docs at [Google Material Design](http://www.google.com/design/spec/components/snackbars-and-toasts.html)

![screenshot](https://github.com/Kennyc1012/SnackBar/blob/master/art/phone.gif)

#Features
- Customization including message, action message, action color, message color, background color, action click handle, animation duration, animation interpolator, typeface, and text appearance   
- Tablet support 
- Swipe to dismiss
- Callbacks for the different SnackBar states (started, actionClicked, finished)
- One Message at a time
- XML Style support


#Using SnackBar
#### Using SnackBar is simple, just one line of code is needed!
```java
SnackBar.show(getActivity(), R.string.hello_world);
```
### Or if you want to set an action
```java
SnackBar.show(getActivity(), R.string.hello_world, R.string.undo, onClickListener);
```
#Customization
### SnackBars can be customized by creating a SnackBarItem with the Builder factory
```java
 new SnackBarItem.Builder(getActivity())
.setMessageResource(R.string.message)
.setActionMessageResource(R.string.action)
.setObject(myObject)
.setActionClickListener(myClickListener)
.setActionMessageColorResource(R.color.my_red)
.setSnackBarMessageColorResource(R.color.my_yellow)
.setSnackBarBackgroundColorResource(R.color.my_green)
.setInterpolatorResource(android.R.interpolator.accelerate_decelerate)
.setMessageTextAppearance(R.style.MessageTextAppearance)
.setActionTextAppearance(R.style.ActionTextAppearance)
.setDuration(5000)
.setSnackBarListener(myListener)
.show();
```

###SnackBars can also be styled via the application theme
The following attributes can be used for styling a SnackBar
```xml
   <attr name="snack_bar_background_color" format="color" />
   <attr name="snack_bar_text_color" format="color" />
   <attr name="snack_bar_text_action_color" format="color" />
   <attr name="snack_bar_duration" format="integer" />
   <attr name="snack_bar_interpolator" format="reference" />
   <attr name="snack_bar_message_typeface" format="string" />
   <attr name="snack_bar_action_typeface" format="string" />
   <attr name="snack_bar_message_text_appearance" format="reference" />
   <attr name="snack_bar_action_text_appearance" format="reference" />
   <attr name="snack_bar_offset" format="reference" />
   ...
   ...
   ...
   ...
   <style name="MyTheme" parent="Theme.AppCompat.Light.NoActionBar">
        <item name="android:windowBackground">@color/background_material_light</item>
        <item name="colorPrimary">@color/colorPrimary</item>
        <item name="colorPrimaryDark">@color/colorPrimaryDark</item>
        <item name="colorAccent">@color/colorAccent</item>
        <item name="snack_bar_text_color">@color/my_color</item>
        <item name="snack_bar_duration">5000</item>
    </style>
```


### Receive callbacks from SnackBars with an Object
```java
// Called when the SnackBar begins to animate
@Override
publc void onSnackBarStarted(Object object){
}

// Called when the SnackBar finishes with its animation
// Will be called if the action button is pressed
@Override
public void onSnackBarFinished(Object object, boolean actionPressed){
}
```

# Canceling SnackBars
### When your activity goes into a Paused or Destroyed state, remove the SnackBars from the queue
```java
SnackBar.cancelSnackBars(getActivity());
``` 


#Including in your project
To include SnackBar in your project, add the following to your build.gradle file.
```groovy
repositories {
   maven { url 'https://dl.bintray.com/kennyc1012/maven' }
}


dependencies {
    compile 'com.kennyc:snackbar:2.5'
}
```


#Contribution
Pull requests are welcomed and encouraged. If you experience any bugs, please [file an issue](https://github.com/Kennyc1012/SnackBar/issues/new)
