# PDF Viewer ANE (Android+iOS)
Pdf Viewer Air Native Extension lets you open pdf files right from your Air mobile apps. On both Android and iOS, it will open a dialog and lets you select which program you wish to use for opening the file. 

[find the latest **asdoc** for this ANE here.](http://myflashlab.github.io/asdoc/com/myflashlab/air/extensions/pdf/package-detail.html)

# Air Usage
```actionscript
import com.myflashlab.air.extensions.pdf.*;

var _ex:PdfViewer = new PdfViewer();
_ex.addEventListener(PdfViewerEvent.STATUS, onStatus);

var result:Boolean = _ex.run(File.cacheDirectory.resolvePath("sample_pdfViewer_ane.pdf"));
trace(result);

private function onStatus(e:PdfViewerEvent):void
{
	trace(e.param);
}
```

# Air .xml manifest
```xml
<uses-sdk android:targetSdkVersion="26"/>
<application>

    <!--
        Other Activities, services, or providers of your Android app.
    -->


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

<application>




<extensions>

	<extensionID>com.myflashlab.air.extensions.pdfViewer</extensionID>

	<!-- dependency ANEs -->
	<extensionID>com.myflashlab.air.extensions.dependency.androidSupport.core</extensionID>
	<extensionID>com.myflashlab.air.extensions.dependency.androidSupport.v4</extensionID>
	<extensionID>com.myflashlab.air.extensions.dependency.overrideAir</extensionID>

</extensions>
```

# Requirements
* Android SDK 15+
* iOS 9.0+
* AIR SDK 30+

# Commercial Version
https://www.myflashlabs.com/product/pdf-reader-ane-adobe-air-native-extension/

[![PDF Viewer ANE](https://www.myflashlabs.com/wp-content/uploads/2015/11/product_adobe-air-ane-extension-pdf-2018-595x738.jpg)](https://www.myflashlabs.com/product/pdf-reader-ane-adobe-air-native-extension/)

# Tech Details
On iOS side, the dialog will always open but on the Android side, if there is no application installed on the device to be able to handle PDF files, the extension will return false. So you should probably promote that user to install Acrobat reader app or any other application that can handle PDF files.

On Android side, your pdf file must be copied to ```File.cacheDirectory```. On iOS side, your file can be anywhere! ```File.applicationDirectory```, ```File.applicationStorageDirectory``` or ```File.documentsDirectory``` they all work.

# Tutorials
[How to embed ANEs into **FlashBuilder**, **FlashCC** and **FlashDevelop**](https://www.youtube.com/watch?v=Oubsb_3F3ec&list=PL_mmSjScdnxnSDTMYb1iDX4LemhIJrt1O)  

# Premium Support #
[![Premium Support package](https://www.myflashlabs.com/wp-content/uploads/2016/06/professional-support.jpg)](https://www.myflashlabs.com/product/myflashlabs-support/)
If you are an [active MyFlashLabs club member](https://www.myflashlabs.com/product/myflashlabs-club-membership/), you will have access to our private and secure support ticket system for all our ANEs. Even if you are not a member, you can still receive premium help if you purchase the [premium support package](https://www.myflashlabs.com/product/myflashlabs-support/).