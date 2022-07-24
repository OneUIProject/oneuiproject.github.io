---
layout: default
title: CollapsingToolbarLayout
parent: material
grand_parent: oneui-core
nav_order: 3
permalink: /sesl/material/collapsingtoolbar/
---

# CollapsingToolbarLayout

CollapsingToolbarLayout is a wrapper for Toolbar which implements a collapsing app bar. It differs from Google's one by introducing a new theme and new features.

This documentation page provides only the additional features, for a complete documentation of this component please take a look at:
- [**Android Developers**](https://developer.android.com/reference/com/google/android/material/appbar/CollapsingToolbarLayout)
- [**Material.io**](https://material.io/components/app-bars-top/android)

We also suggest you to read Samsung's One UI design guidelines before you implement this in your app:
- [**Samsung Developers**](https://developer.samsung.com/one-ui/comp/app-bar.html)
- [**One UI Design Guidelines**](https://design.samsung.com/global/contents/one-ui/download/oneui_design_guide_eng.pdf) (page 18-28)

## Styles

- ### Widget.Design.CollapsingToolbar
<img src="https://raw.githubusercontent.com/OneUIProject/oneuiproject.github.io/main/assets/material/collapsingtoolbar/collapsingtoolbar-dark.png" width="50%"/>

- ### Widget.Design.Light.CollapsingToolbar
<img src="https://raw.githubusercontent.com/OneUIProject/oneuiproject.github.io/main/assets/material/collapsingtoolbar/collapsingtoolbar-light.png" width="50%"/>

Avoid using "Widget.MaterialComponents.*" styles.

## XML attributes

- ### CollapsingToolbarLayout_extendedTitleEnabled

  Sets whether this view should display its own title.

- ### CollapsingToolbarLayout_extendedTitleTextAppearance

  Sets text-specific styling for the title text.

- ### CollapsingToolbarLayout_extendedSubtitleTextAppearance

  Sets text-specific styling for the subtitle text.

- ### CollapsingToolbarLayout_subtitle

  Sets the subtitle of this view.

## Methods

- Enable/disable the fade effect for the toolbar title.

```java
public void seslEnableFadeToolbarTitle(boolean enabled)
```

- Set the subtitle of this view.

```java
public void seslSetSubtitle(@StringRes int resId)
public void seslSetSubtitle(CharSequence subtitle)
```

- Get the subtitle of this view.

```java
public CharSequence getSubTitle()
```

- Set a custom title view, requires a [CollapsingToolbarLayout.LayoutParams](#collapsingtoolbarlayoutlayoutparams) instance.

<img src="https://raw.githubusercontent.com/OneUIProject/oneuiproject.github.io/main/assets/material/collapsingtoolbar/collapsingtoolbar-customview.gif" width="40%"/>

```java
public void seslSetCustomTitleView(View view, LayoutParams params)
```

- Set a custom subtitle view.

```java
public void seslSetCustomSubtitle(View view)
```

- Get the custom subtitle view.

```java
public View seslGetCustomSubtitle()
```

# CollapsingToolbarLayout.LayoutParams

This documentation page provides only the additional features, for a complete documentation of this component please take a look at [**Google's official documentation**](https://developer.android.com/reference/com/google/android/material/appbar/CollapsingToolbarLayout.LayoutParams).

## XML attributes

- ### CollapsingToolbarLayout_Layout_isCustomTitle

  Sets whether or not the view should be used as a custom title view.

## Methods

- Set whether or not the view should be used as a custom title view.

```java
public void seslSetIsTitleCustom(Boolean isCustom)
```

- Get if the view is being used as a custom title view.

```java
public boolean seslIsTitleCustom()
```
