---
layout: default
title: TabLayout
parent: material
grand_parent: oneui-core
nav_order: 5
permalink: /sesl/material/tablayout/
---

# TabLayout

TabLayout provides a horizontal layout to display tabs, it is used by Samsung in their apps to navigate through different screens in the same Activity. It differs from Google's one by introducing a new theme and new features.

This documentation page provides only the additional features, for a complete documentation of this component please take a look at:
- [**Android Developers**](https://developer.android.com/reference/com/google/android/material/tabs/TabLayout)
- [**Material.io**](https://material.io/components/tabs/android)

We also suggest you to read Samsung's One UI design guidelines before you implement this in your app:
- [**Samsung Developers**](https://developer.samsung.com/one-ui/comp/bottom-navigation.html)
- [**One UI Design Guidelines**](https://design.samsung.com/global/contents/one-ui/download/oneui_design_guide_eng.pdf) (page 31-34)

## Styles

- ### Widget.Design.TabLayout
<img src="https://raw.githubusercontent.com/BlackMesa123/blackmesa123.github.io/main/assets/material/tablayout/tablayout-dark.png" width="50%"/>

- ### Widget.Design.TabLayout.Light
<img src="https://raw.githubusercontent.com/BlackMesa123/blackmesa123.github.io/main/assets/material/tablayout/tablayout-light.png" width="50%"/>

Avoid using "Widget.MaterialComponents.*" styles.

## XML attributes

- ### TabLayout_seslTabSubTextAppearance

  Sets text-specific styling for sub tabs secondary text.

- ### TabLayout_seslTabSubTextColor

  Sets sub tabs secondary text color.

- ### TabLayout_seslTabSelectedSubTextColor

  Sets sub tabs secondary text selected color.

## Methods

- Set a custom size for all the tabs.

```java
public void seslSetTabWidth(int width)
```

- Set a custom icon margin for all the tabs.

```java
public void seslSetIconTextGap(int gap)
```

- **Deprecated.** Set tabs text color, with an option to invalidate all the tabs.

```java
public void seslSetTabTextColor(ColorStateList textColor, boolean updateTabView)
```

- Show or hide a badge without text for the tab at the specified index.

<img src="https://raw.githubusercontent.com/BlackMesa123/blackmesa123.github.io/main/assets/material/tablayout/tablayout-dotbadge-light.png" width="15%"/> <img src="https://raw.githubusercontent.com/BlackMesa123/blackmesa123.github.io/main/assets/material/tablayout/tablayout-dotbadge-dark.png" width="15%"/>

```java
public void seslShowDotBadge(int index, boolean show)
```

- Show or hide a badge with text for the tab at the specified index.

<img src="https://raw.githubusercontent.com/BlackMesa123/blackmesa123.github.io/main/assets/material/tablayout/tablayout-badge-light.png" width="15%"/> <img src="https://raw.githubusercontent.com/BlackMesa123/blackmesa123.github.io/main/assets/material/tablayout/tablayout-badge-dark.png" width="15%"/>

```java
public void seslShowBadge(int index, boolean show, String content)
public void seslShowBadge(int index, boolean show, String content, String contentDescription)
```

- Set tabs badge background color.

<img src="https://raw.githubusercontent.com/BlackMesa123/blackmesa123.github.io/main/assets/material/tablayout/tablayout-badgecolor-light.png" width="15%"/> <img src="https://raw.githubusercontent.com/BlackMesa123/blackmesa123.github.io/main/assets/material/tablayout/tablayout-badgecolor-dark.png" width="15%"/>

```java
public void seslSetBadgeColor(int color)
```

- Set tabs badge text color.

<img src="https://raw.githubusercontent.com/BlackMesa123/blackmesa123.github.io/main/assets/material/tablayout/tablayout-badgetext-light.png" width="15%"/> <img src="https://raw.githubusercontent.com/BlackMesa123/blackmesa123.github.io/main/assets/material/tablayout/tablayout-badgetext-dark.png" width="15%"/>

```java
public void seslSetBadgeTextColor(int color)
```

- Change the view style to sub tabs.

<img src="https://raw.githubusercontent.com/BlackMesa123/blackmesa123.github.io/main/assets/material/tablayout/tablayout-sub-light.png" width="40%"/> <img src="https://raw.githubusercontent.com/BlackMesa123/blackmesa123.github.io/main/assets/material/tablayout/tablayout-sub-dark.png" width="40%"/>

```java
public void seslSetSubTabStyle()
```

- Set a custom height for the sub tabs indicator.

```java
public void seslSetSubTabIndicatorHeight(int heightPixel)
```

- Set sub tabs indicator background color.

<img src="https://raw.githubusercontent.com/BlackMesa123/blackmesa123.github.io/main/assets/material/tablayout/tablayout-subcolor-light.png" width="20%"/> <img src="https://raw.githubusercontent.com/BlackMesa123/blackmesa123.github.io/main/assets/material/tablayout/tablayout-subcolor-dark.png" width="20%"/>

```java
public void seslSetSubTabSelectedIndicatorColor(int color)
```

- Set sub tabs secondary text color.

<img src="https://raw.githubusercontent.com/BlackMesa123/blackmesa123.github.io/main/assets/material/tablayout/tablayout-subtext-light.png" width="20%"/> <img src="https://raw.githubusercontent.com/BlackMesa123/blackmesa123.github.io/main/assets/material/tablayout/tablayout-subtext-dark.png" width="20%"/>

```java
public void seslSetTabSubTextColors(@Nullable ColorStateList color)
public void seslSetTabSubTextColors(int defaultColor, int selectedColor)
```

- Get sub tabs secondary text color.

```java
public ColorStateList seslGetTabSubTextColors()
```

## Additional tab modes

Samsung's TabLayout provides two additional [tab modes](https://developer.android.com/reference/com/google/android/material/tabs/TabLayout#setTabMode(int)):

- **SESL_MODE_FIXED_AUTO**: similar to [MODE_FIXED](https://developer.android.com/reference/com/google/android/material/tabs/TabLayout#MODE_FIXED), will automatically switch to [MODE_SCROLLABLE](https://developer.android.com/reference/com/google/android/material/tabs/TabLayout#MODE_SCROLLABLE) and resize the tabs depending its content when they won't fit anymore in the screen.
- **SESL_MODE_WEIGHT_AUTO**: always resizes the tabs depending its content, will automatically switch to [MODE_SCROLLABLE](https://developer.android.com/reference/com/google/android/material/tabs/TabLayout#MODE_SCROLLABLE) when they won't fit anymore in the screen.

# TabLayout.Tab

A TabLayout's Tab instance. It differs from Google one by introducing new features.

This documentation page provides only the additional features, for a complete documentation of this component please take a look at [**Google's official documentation**](https://developer.android.com/reference/com/google/android/material/tabs/TabLayout.Tab).

## Methods

- Get the secondary text of this tab.

```java
public CharSequence seslGetSubText()
```

- Set the secondary text displayed on this tab, will show up only with sub tab style.

```java
public Tab seslSetSubText(@Nullable CharSequence text)
```

- Get the title TextView of this tab.

```java
public TextView seslGetTextView()
```

- Get the secondary text TextView of this tab.

```java
public TextView seslGetSubTextView()
```