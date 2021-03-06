# PDF viewer Adobe Air Native Extension

*Aug 01, 2020 - v4.0.0*
- Upgrade dependencies to the latest versions.
- Fixed some minor issues and refactor native codes.

*Apr 05, 2020 - V3.0.0*
- Added Androidx dependencies instead of android support

*Aug 4, 2019 - V2.2.31*
* Added Android 64-bit support
* Supports min iOS 10+

*Nov 18, 2018 - V2.2.3*
* Works with OverrideAir ANE V5.6.1 or higher
* Works with ANELAB V1.1.26 or higher

*Sep 23, 2018 - V2.2.2*
* removed androidSupport dependency then added `androidSupport-core.ane` and `androidSupport-v4.ane`.

*Jul 18, 2018 - V2.2.1*
* Fixed conflict between this ANE and the videoPlayer ANE caused by the <provider> tag. We have now overwriten the Provider class so the conflict will be correctly bypassed.
* make sure the `<provider>` tag is under the `<application>` tag in the Android part.
* Also changed the provider path xml file name to `@xml/pdf_viewer_ane_provider_paths`. Make sure you are using this name rather than the older one.
```xml
<!--
    Change [YOUR_PACKAGE_ID] to your own applicationID but keep
    ".provider" at the end. [YOUR_PACKAGE_ID].provider
-->
<provider
    android:name="com.myflashlabs.pdfViewer.AnePdfViewerProvider"
    android:authorities="[YOUR_PACKAGE_ID].provider"
    android:exported="false"
    android:grantUriPermissions="true">
    <meta-data
        android:name="android.support.FILE_PROVIDER_PATHS"
        android:resource="@xml/pdf_viewer_ane_provider_paths"/>
</provider>
```

*Jul 11, 2018 - V2.2.0*
* On Android, supporting targetSdkVersion is now 26 like below. Lower versions work also but you are recommended to use V26
```xml
<uses-sdk android:targetSdkVersion="26"/>
```
* The [permission ANE](https://github.com/myflashlab/PermissionCheck-ANE/) is no longer requierd and you no longer need to ask for external access. **Remove** the following tag from your manifest: `<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"/>`
* On Android, pdf files must be copied to `File.cacheDirectory` from now on. make sure you are updating your AS3 code.
* On Android, you must add the following `<provider>` tag.
```xml
<provider
    android:name="android.support.v4.content.FileProvider"
    android:authorities="[YOUR_PACKAGE_ID].provider"
    android:exported="false"
    android:grantUriPermissions="true">
    <meta-data
        android:name="android.support.FILE_PROVIDER_PATHS"
        android:resource="@xml/provider_paths"/>
</provider>
```

*Mar 22, 2017 - V2.1.2*
* Optimized for [ANE-LAB software](https://github.com/myflashlab/ANE-LAB).

*Mar 22, 2017 - V2.1.1*
* Min iOS version to support this ANE is 8.0 from now on.
* Even the iOS side now is also dependent on the OverrideAir.ane
* Fixed the white screen problem on iOS builds.

*Feb 02, 2016 - V2.0.1*
* Fixed a bug on iPads where the Air blured interface was not cleared on some random occasions

*Jan 26, 2016 - V2.0*
* Added iOS support
* upgraded the Android side to support opening pdf files in any app that can handle these file types

*Nov 03, 2015 - V1.9*
* doitflash devs merged into MyFLashLab Team.

*May 01, 2013 - V1.0*
* beginning of the journey!
