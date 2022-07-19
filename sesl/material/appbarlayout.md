---
layout: default
title: AppBarLayout
parent: material
grand_parent: oneui-core
nav_order: 1
permalink: /sesl/material/appbarlayout/
---

# AppBarLayout

AppBarLayout is a vertical LinearLayout which implements many of the features of material designs app bar concept. It differs from Google's one by introducing new features.

This documentation page provides only the additional features, for a complete documentation of this component please take a look at:
- [**Android Developers**](https://developer.android.com/reference/com/google/android/material/appbar/AppBarLayout)
- [**Material.io**](https://material.io/components/app-bars-top/android)

We also suggest you to read Samsung's One UI design guidelines before you implement this in your app:
- [**Samsung Developers**](https://developer.samsung.com/one-ui/comp/app-bar.html)
- [**One UI Design Guidelines**](https://design.samsung.com/global/contents/one-ui/download/oneui_design_guide_eng.pdf) (page 18-28)

## XML attributes

- ### AppBarLayout_seslUseCustomHeight

  Enables the use of a custom layout_width or height proportion for this view.

- ### AppBarLayout_seslHeightProportion

  Sets a custom height proportion size.

- ### AppBarLayout_seslUseCustomPadding

  Enables the use of a custom padding value for this view.

## Methods

- Set a custom height proportion size, with an option to enable the use of a custom value.

```java
public void seslSetCustomHeightProportion(boolean enabled, float proportion)
```

- Get the currently used height proportion size.

```java
public float seslGetHeightProPortion()
```

- Set a custom height size in pixel.

```java
public void seslSetCustomHeight(int height)
```

- Set a custom collapsed height, note this will only affect the scroll behaviour.

```java
public void seslSetCollapsedHeight(float height)
```

- Get the currently used collapsed height.

```java
public float seslGetCollapsedHeight()
```

- Get the current SeslAppbarState instance.

```java
public SeslAppbarState seslGetAppBarState()
```

- Wrapper for [*setExpanded(boolean)*](https://developer.android.com/reference/com/google/android/material/appbar/AppBarLayout#setExpanded(boolean)).

```java
public void seslSetExpanded(boolean expanded)
```

- Get if the AppBar is collapsed.

```java
public boolean seslIsCollapsed()
```

- *To-be-documented* Immersive scroll methods. **Available only from API 30 and above.**

```java
public void seslAddOnImmOffsetChangedListener(@Nullable SeslBaseOnImmOffsetChangedListener listener)
public void seslAddOnImmOffsetChangedListener(SeslOnImmOffsetChangedListener listener)
public void seslRemoveOnImmOffsetChangedListener(SeslBaseOnImmOffsetChangedListener listener)
public void seslRemoveOnImmOffsetChangedListener(OnOffsetChangedListener listener)
public void seslReserveImmersiveDetachOption(int flag)
@Deprecated public void seslRestoreTopAndBottom(View view)
public boolean seslHaveImmersiveBehavior()
public void seslSetWindowInsetsAnimationCallback(Object callback)
public void seslRestoreTopAndBottom()
public void seslRestoreTopAndBottom(boolean restore)
public void resetAppBarAndInsets()
public void seslResetAppBarAndInsets(boolean force)
public void seslCancelWindowInsetsAnimationController()
public void seslImmHideStatusBarForLandscape(boolean hide)
@Deprecated public void seslSetBottomView(View view, View bottomView)
public void seslSetBottomView(View bottomView)
public void seslActivateImmersiveScroll(boolean activate, boolean byUser)
public void seslSetImmersiveScroll(boolean activate, boolean byUser)
public void seslActivateImmersiveScroll(boolean activate)
public void seslSetImmersiveScroll(boolean activate)
public boolean isActivatedImmsersiveScroll()
public boolean seslGetImmersiveScroll()
public void seslSetTCScrollRange(int range)
```

# AppBarLayout.LayoutParams

This documentation page provides only the additional features, for a complete documentation of this component please take a look at [**Google's official documentation**](https://developer.android.com/reference/com/google/android/material/appbar/AppBarLayout.LayoutParams).

## Constants

- ### SESL_SCROLL_FLAG_NO_SCROLL_HOLD

  Disables scroll hold behaviour.

- ### SESL_SCROLL_FLAG_NO_SNAP

  Disables the snap scrolling behaviour.