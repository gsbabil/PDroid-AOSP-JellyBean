Each [Android][1] application requires a set of [various permissions][2] to be granted when the application installs. Either the user has to accept these permission-requests or the user has to abort installation. In essence, accepting all the permissions requested by an application is the only option left if the user wants to install and use it. Currently there is no way on Android to block access to any permission for an installed application once they are granted. This is where [PDroid][3] comes in.

[PDroid][4] is a privacy preserving application for Android that allows user to block permissions of the installed applications. PDroid has two parts. Simply speaking, the first and the most important part of PDroid modifies the Android framework and core libraries so that the permission requests from the applications can be intercepted and the decision whether to accept or denial can be made by PDroid. On the other hand, the [PDroid user application][5], downloadable from the [Google Play Store][6], provides the user interface so that the user can select, modify, allow or grant permissions of the applications installed on the system.

PDroid patch and the application were originally developed by the [XDA][7] developer "[svyat][8]". The original stable PDroid patch was created for [Gingerbread][9] (Android version 2.3.4). Later it was ported to [Ice Cream Sandwich][10] (Android version 4.0.4) by another XDA developer known as "[pastime1971][11]". My contribution here is the same as what [pastime1971][11] has done for Ice Cream Sandwich. I have ported the PDroid to the latest [Android Jelly Bean][12] (version 4.1.1).

**PDroid with Jelly Bean Build Instructions:**

The instructions below are for Ubuntu Linux [11]. 

 - Initialize your build environment as per [this link][13].
 - Download your Android source as per [this link][14]. Since we will be building Jelly Bean, you need to initialize your repo as `repo init -u https://android.googlesource.com/platform/manifest -b android-4.1.1_r4`. 4.1.1_r4 is the latest revision of Jelly Bean as of now.

 - Download my patch by doing `wget https://github.com/gsbabil/PDroid-AOSP-JellyBean/raw/master/ pdroid-1.32-aosp-4.1.1_rf.diff”`
 - Apply the patch by doing a `patch –p1 < pdroid-1.32-aosp-4.1.1_rf.diff`
 - Now you can start the build by doing a `source build/envsetup.sh; lunch; make;`



  [1]: http://www.android.com
  [2]: http://developer.android.com/reference/android/Manifest.permission.html
  [3]: http://forum.xda-developers.com/showthread.php?t=1357056
  [4]: http://forum.xda-developers.com/showthread.php?t=1357056
  [5]: https://play.google.com/store/apps/details?id=com.privacy.pdroid&hl=en
  [6]: https://play.google.com/store
  [7]: http://www.xda-developers.com/
  [8]: http://forum.xda-developers.com/member.php?u=2605967
  [9]: http://en.wikipedia.org/wiki/Android_version_history#Android_2.3.x_Gingerbread
  [10]: http://en.wikipedia.org/wiki/Android_version_history#Android_4.0.x_Ice_Cream_Sandwich
  [11]: http://forum.xda-developers.com/member.php?u=4005966
  [12]: http://en.wikipedia.org/wiki/Android_version_history#Android_4.1.x_Jelly_Bean
  [13]: http://source.android.com/source/initializing.html
  [14]: http://source.android.com/source/downloading.html