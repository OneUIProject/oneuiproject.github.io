---
layout: default
title: BottomNavigationView
parent: material
grand_parent: oneui-core
nav_order: 2
permalink: /sesl/material/bottomnavigation/
---

# BottomNavigationView

BottomNavigationView is used in Samsung apps to display bottom actions during an event or as a navigation bar for apps with multiple pages (see Samsung Health, Game Launcher...). It differs from Google's one by introducing a new theme and new features.

This documentation page provides only the additional features, for a complete documentation of this component please take a look at:
- [**Android Developers**](https://developer.android.com/reference/com/google/android/material/bottomnavigation/BottomNavigationView)
- [**Material.io**](https://material.io/components/bottom-navigation/android)

We also suggest you to read Samsung's One UI design guidelines before you implement this in your app:
- [**Samsung Developers**](https://developer.samsung.com/one-ui/comp/bottom-bar.html)
- [**One UI Design Guidelines**](https://design.samsung.com/global/contents/one-ui/download/oneui_design_guide_eng.pdf) (page 29-30)

## Styles

- ### Widget.Design.BottomNavigationView
<img src="https://raw.githubusercontent.com/OneUIProject/oneuiproject.github.io/main/assets/material/bottomnav/bottomnav-dark.png" width="50%"/>

- ### Widget.Design.Light.BottomNavigationView
<img src="https://raw.githubusercontent.com/OneUIProject/oneuiproject.github.io/main/assets/material/bottomnav/bottomnav-light.png" width="50%"/>

- ### Widget.Design.BottomNavigationView.Text
<img src="https://raw.githubusercontent.com/OneUIProject/oneuiproject.github.io/main/assets/material/bottomnav/bottomnav-text-dark.png" width="50%"/>

- ### Widget.Design.Light.BottomNavigationView.Text
<img src="https://raw.githubusercontent.com/OneUIProject/oneuiproject.github.io/main/assets/material/bottomnav/bottomnav-text-light.png" width="50%"/>

Avoid using "Widget.MaterialComponents.*" styles.

## XML attributes

- ### NavigationBarView_seslViewType

  Sets item view layout type.

- ### NavigationBarView_seslLabelTextAppearance

  Sets text-specific styling for the item text label.

## Constants

- ### SESL_TYPE_ICON_LABEL
  Default item view type.

- ### SESL_TYPE_LABEL_ONLY
  Label-only item view type.

## Methods

- Set item view layout type.

```java
public void seslSetViewType(int viewType)
```

- **Deprecated.** Set whether or not the item layout has an icon.

```java
public void seslSetHasIcon(boolean hasIcon)
```

- Get if the Overflow menu button is available.

```java
public boolean seslHasOverflowButton()
```

- Show the Overflow menu popup if available.

```java
public void seslShowOverflowMenu()
```

- Get if the Overflow menu popup is showing.

```java
public boolean seslIsOverflowShowing()
```

- Hide the Overflow menu popup.

```java
public void seslHideOverflowMenu()
```

- Get the current Overflow menu instance.

```java
public MenuBuilder seslGetOverflowMenu()
```

- Show the group divider in the Overflow menu.

<img src="https://raw.githubusercontent.com/OneUIProject/oneuiproject.github.io/main/assets/material/bottomnav/bottomnav-overflow.jpg" width="25%"/>

```java
public void seslSetGroupDividerEnabled(boolean enabled)
```

- Wrapper for [*setItemTextAppearanceInactive(int)*](https://developer.android.com/reference/com/google/android/material/navigation/NavigationBarView#setItemTextAppearanceInactive(int)).

```java
public void seslSetLabelTextAppearance(@StyleRes int textAppearanceRes)
```

- Get the current label text appearance resource id.

```java
public int seslGetLabelTextAppearance()
```

- Animate on menu changes.

<img src="https://raw.githubusercontent.com/OneUIProject/oneuiproject.github.io/main/assets/material/bottomnav/bottomnav-anim.gif" width="40%"/>

```java
public void seslSetUpdateAnimation(boolean enabled)
```

## Item badge

This view support the SeslMenuItem interface to show a badge with text for each MenuItem:

<img src="https://raw.githubusercontent.com/OneUIProject/oneuiproject.github.io/main/assets/material/bottomnav/bottomnav-badge-light.png" width="15%"/> <img src="https://raw.githubusercontent.com/OneUIProject/oneuiproject.github.io/main/assets/material/bottomnav/bottomnav-badge-dark.png" width="15%"/>

```java
SeslMenuItem menuItem = (SeslMenuItem) bottomNavView.getMenu().findItem(R.id.item_1);
menuItem.setBadgeText("N");
```
