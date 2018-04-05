# Firebase Auth UI Customization:

List of default styles from FirebaseUI:

https://github.com/firebase/FirebaseUI-Android/blob/master/auth/src/main/res/values/styles.xml

https://firebase.google.com/docs/auth/android/manage-users#update_a_users_profile

-------Custom Style-------

    <style name="FullscreenTheme" parent="AppTheme">
        <item name="android:actionBarStyle">@style/FullscreenActionBarStyle</item>
        <item name="android:windowActionBarOverlay">true</item>
        <item name="android:windowBackground">@drawable/bg_login</item>
        <item name="metaButtonBarStyle">?android:attr/buttonBarStyle</item>
        <item name="metaButtonBarButtonStyle">?android:attr/buttonBarButtonStyle</item>
        <item name="windowActionBar">false</item>
        <item name="windowNoTitle">true</item>
        <item name="colorControlNormal">@color/colorWhite</item>
        <item name="colorControlActivated">@color/colorWhite</item>
        <item name="colorControlHighlight">@color/colorWhite</item>
    </style>

    <style name="FullscreenActionBarStyle" parent="Widget.AppCompat.ActionBar">
        <item name="android:background">@color/colorPrimary</item>
    </style>
    
So you can create a beautiful background with a photo and a logo over it by using drawables, 
like this (name this file bg_login, is referenced above):

    <?xml version="1.0" encoding="utf-8"?>
    <layer-list xmlns:android="http://schemas.android.com/apk/res/android">
        <item android:drawable="@mipmap/cool_photo"/>
        <item android:top="120dp">
            <bitmap
                android:src="@mipmap/your_logo"
                android:gravity="top|center_horizontal" />
        </item>
    </layer-list>
    
Customizing Components of Firebase UI by overriding Firebase Theme:

    <style name="FirebaseUI.EditText">
        <item name="android:paddingBottom">14dp</item>
        <item name="android:paddingTop">14dp</item>
        <item name="android:layout_width">match_parent</item>
        <item name="android:layout_height">wrap_content</item>
        <item name="colorControlActivated">@color/colorWhite</item>
        <item name="colorControlHighlight">@color/colorWhite</item>
        <item name="android:textColorHint">@color/colorWhite</item>
        <item name="android:textColor">@color/colorWhite</item>
    </style>

    <style name="FirebaseUI.Text.TextInputLayout" parent="@style/FirebaseUI.EditText" />

    <style name="FirebaseUI.Text.HintText" parent="@style/FirebaseUI.EditText" />
    
    <style name="FirebaseUI.Button" parent="@style/FullscreenTheme">
        <item name="android:background">@drawable/bg_btn_accent</item>
        <item name="android:layout_width">wrap_content</item>
        <item name="android:layout_gravity">right</item>
        <item name="android:layout_height">36dp</item>
        <item name="android:layout_margin">8dp</item>
        <item name="android:textColor">@color/colorWhite</item>
        <item name="android:textAllCaps">true</item>
        <item name="android:radius">2dp</item>
    </style>
