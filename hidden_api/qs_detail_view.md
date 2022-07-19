---
layout: default
title: Quick Settings Detail View
parent: Hidden Samsung API
nav_order: 2
permalink: /hidden-api/qs-detail-view/
---

## Quick Settings Detail View

<img align="left" src="/assets/hidden_api/qs_detail_view/preview.png" width="25%"/>

Add an extended view to your Quick Settings [Tile](https://developer.android.com/reference/android/service/quicksettings/Tile), which gets displayed by clicking on the tile label below the icon, like the Wi-Fi or Bluetooth tile.

For the Detail View you'll need to know how to use [RemoteViews](https://developer.android.com/reference/android/widget/RemoteViews) and how they work, since this is used for the view layout and functionality.

<br clear="left"/>

### How to add it in your app

Override the following methods inside your service class which is extending [TileService](https://developer.android.com/reference/android/service/quicksettings/TileService). These will be called by the system to retrieve the necessary information for the detail view. They aren't all required and if not provided the default will be used.

- Return the title.
```java
public CharSequence semGetDetailViewTitle() {
    return null;
}
```

- If returning `true`, the main switchbar will be shown.
```java
public boolean semIsToggleButtonExists() {
    return true;
}
```

- Return the switchbar checked state at start. This only gets called once. See below to toggle it manually later on.
```java
public boolean semIsToggleButtonChecked() {
    return false;
}
```

- Return the RemoteViews for the Detail View.
```java
public RemoteViews semGetDetailView() {
    return null;
}
```

- Return the Intent which should be started when clicking the `Details` button. It will also replace the [long click action](https://developer.android.com/reference/android/service/quicksettings/TileService#ACTION_QS_TILE_PREFERENCES) defined in manifest. If `null` the button won't be shown.
```java
public Intent semGetSettingsIntent() {
    return null;
}
```

- This will get called each time you toggle the switchbar and therefore serves as listener.
```java
public void semSetToggleButtonChecked(boolean checked) {
}
```

- Unknown. If somebody finds out what it does, please let us know :).
```java
public CharSequence semGetDetailViewSettingButtonName() {
    return null;
}
```

Inside your tile service class you can trigger an update for the Detail View with this piece of code.
```java
try {
    getClass().getMethod("semUpdateDetailView").invoke(this);
} catch (Exception e) {
    e.printStackTrace();
}
```
And to toggle and enable/disable the main switchbar use this.
```java
try {
    getClass().getMethod("semFireToggleStateChanged", boolean.class, boolean.class).invoke(this, checked, enabled);
} catch (Exception e) {
    e.printStackTrace();
}
```