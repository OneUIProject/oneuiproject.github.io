---
layout: default
title: Lock screen Widgets
parent: Hidden Samsung API
nav_order: 1
permalink: /hidden-api/facewidget/
---

## Lock screen Widgets

Aka Face widgets. This will allow your app to display a widget on the lock screen, like the calendar, music player or the weather forecast. The system settings for this can be found at `Settings > Lock screen > Widgets`. For the Lock screen widgets you'll need to know how to use [RemoteViews](https://developer.android.com/reference/android/widget/RemoteViews) and how they work, since this is used for the widget layout and functionality.

### How to add it in your app

Inside `AndroidManifest.xml` you need to add the permission, the meta-data and a receiver.
```xml
<manifest>

    <uses-permission android:name="com.samsung.systemui.permission.FACE_WIDGET" />

    <application>

        <meta-data
            android:name="com.samsung.systemui.facewidget.executable"
            android:resource="@raw/facewidgets" />

        <receiver
            android:name=".FaceWidgetReceiver"
            android:exported="true">
            <intent-filter>
                <action android:name="com.samsung.android.intent.action.REQUEST_SERVICEBOX_REMOTEVIEWS" />
            </intent-filter>
        </receiver>

    </application>

</manifest>
```

Add a file called `facewidgets.json` in your res/raw directory. This file will contain a list of widgets and their information needed by the system.
```json
{
  "facewidget": { //this is the 'pageId' of the widget
    "labelResNameInSetting": "widget_title", //the string resource for the title. Equivalent to R.string.widget_title or @string/widget_title
    "actionDetailSetting": "<your_package>.<your_action>" //this is optional. It's the intent action for a settings activity
  }
}
```

If you're using `actionDetailSetting`, you'll have to add an intent filter to the activity you want to launch with it.
```xml
<intent-filter>
    <action android:name="<your_package>.<your_action>" />
    <category android:name="android.intent.category.DEFAULT" />
</intent-filter>
```

You can also have multiple widgets per app, for this simply add more json objects to the list in `facewidgets.json`.
```json
{
  "facewidget1": {
    "labelResNameInSetting": "widget1_title",
    "actionDetailSetting": "<your_package>.<your_action>"
  },
  "facewidget2": {
    "labelResNameInSetting": "widget2_title",
    "actionDetailSetting": "<your_package>.<your_action>"
  },
  ...
}
```

The code for receiver you defined in the `AndroidManifest.xml` (`FaceWidgetReceiver.java`). This will be called when the system requests an update for the widgets. 
```java
public class FaceWidgetReceiver extends BroadcastReceiver {

    @Override
    public final void onReceive(Context context, Intent intent) {
        if ("com.samsung.android.intent.action.REQUEST_SERVICEBOX_REMOTEVIEWS".equals(intent.getAction())) {
            //code will be executed when the system ask for an update
        }
    }

}
```
The intent has an extra called 'pageId', which you will need later when responding. This is the same pageId you defined for your widgets in the `facewidgets.json` file. You can get it like this.
```java
intent.getStringExtra("pageId")
```

After a request from the system, it expects a response from your app. For this you simply need to run this piece of code.
```java
Intent intent = new Intent("com.samsung.android.intent.action.RESPONSE_SERVICEBOX_REMOTEVIEWS");
intent.setPackage("com.android.systemui");
intent.putExtra("package", context.getPackageName()); //your app packageName
intent.putExtra("pageId", pageId); //the pageId which you received in the BroadcastReceiver
intent.putExtra("show", true);
intent.putExtra("origin", lockRemoteViews); //the RemoteViews for the lockscreen
intent.putExtra("aod", aodRemoteViews); //the RemoteViews for the AOD
context.sendBroadcast(intent);
```
`origin` and `aod` are [RemoteViews](https://developer.android.com/reference/android/widget/RemoteViews). The only difference between these two should be the background.

Background drawables:
- Light Mode

```xml
<?xml version="1.0" encoding="utf-8"?>
<shape xmlns:android="http://schemas.android.com/apk/res/android"
    android:shape="rectangle">
    <corners android:radius="22.0dip" />
    <solid android:color="#e6fafafa" />
</shape>
```

- Dark Mode

```xml
<?xml version="1.0" encoding="utf-8"?>
<shape xmlns:android="http://schemas.android.com/apk/res/android"
    android:shape="rectangle">
    <corners android:radius="22.0dip" />
    <solid android:color="#99010101" />
</shape>
```

- AOD

```xml
<?xml version="1.0" encoding="utf-8"?>
<shape xmlns:android="http://schemas.android.com/apk/res/android"
    android:shape="rectangle">
    <corners android:radius="22.0dip" />
    <solid android:color="#ff171717" />
</shape>
```