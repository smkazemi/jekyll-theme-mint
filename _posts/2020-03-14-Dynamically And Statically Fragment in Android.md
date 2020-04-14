---
layout: post
---

There is two type of Fragment in andriod ; Dynamically And statically

# Statically

Use to show one fragment in an activity

## steps :

**1 - Create a fragment**

From *New -> Fragment* create a blank fragment and named this *TestFragment* .

no need do any changes on fragment class or it's layout, this is just for test.

**2 - show fragment in actiity**

Put on activity's layout a fragment tag :

![](/images/fragmentTag.png)

>Note : place your package name instead of *com.example.testkotlinapp* in name attribute

Now you can see your fragment in ativity , no need to other codes

# Dynamically

In this case we implement fragment by code, without use ``<fragment>`` tag in xml layout, advantage of this is being able to remove the fragment at runtime.

## steps :

**1- Specify space in activity for holding fragment**

In activity layout you must Assign a layout holder for holding fragment view e.g. RelativeView and it can be place any where in activuty layout.

**2- Attach fragment by code to its view holder**

First should create instance of fragment class then with fragment manager attach this to the view that is to contain fragment 
For example assume `FragmentOne()` as fragment class and `LineatLayout1` as view that is contain it fragment

```kotlin
val firstFragment = FragmentOne()
firstFragment.arguments = intent.extras
val transaction = fragmentManager.beginTransaction()
transaction.add(R.id.LinearLayout1, firstFragment)
transaction.commit()
```
You can see also there is ability to send extra to the fragment class

# Final Project
[This project](https://github.com/smkazemi/Android-Simple-Exapmles/tree/master/FragmentExample) is a runnable android app that implemented statically and dynamically fragment in kotlin.