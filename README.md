# PDF Viewer ANE V2.1.2 (Android+iOS)
Pdf Viewer Air Native Extension lets you open pdf files right from your Air mobile apps. On both Android and iOS, it will open a dialog and lets you select which program you wish to use for opening the file. 

# asdoc
[find the latest asdoc for this ANE here.](http://myflashlab.github.io/asdoc/com/myflashlab/air/extensions/pdf/package-detail.html)

[Download demo ANE](https://github.com/myflashlab/PDF-ANE/tree/master/AIR/lib)

# Air Usage
```actionscript
import com.myflashlab.air.extensions.pdf.PdfViewer;
import com.myflashlab.air.extensions.pdf.PdfViewerEvent;

var _ex:PdfViewer = new PdfViewer();
_ex.addEventListener(PdfViewerEvent.STATUS, onStatus);

var result:Boolean = _ex.run(File.documentsDirectory.resolvePath("sample_pdfViewer_ane.pdf"));
trace(result);

private function onStatus(e:PdfViewerEvent):void
{
	trace(e.param);
}
```

# Air .xml manifest
```xml
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"/>
```

# Requirements
* Android SDK 15 or higher
* iOS 9.0 or higher
* AIR SDK 27+

# Commercial Version
http://www.myflashlabs.com/product/pdf-reader-ane-adobe-air-native-extension/

![PDF Viewer ANE](http://www.myflashlabs.com/wp-content/uploads/2015/11/product_adobe-air-ane-extension-pdf-1-595x738.jpg)

# Tech Details
On iOS side, the dialog will always open but on the Android side, if there is no application installed on the device to be able to handle PDF files, the extension will return false. So you should probably promote that user to install Acrobat reader app or any other application that can handle PDF files.

On Android side, you cannot open a pdf file in another app unless the pdf file is somewhere public. which means your file must be copied into ```File.documentsDirectory``` before you can open it. On iOS side, your file can be anywhere! ```File.applicationDirectory```, ```File.applicationStorageDirectory``` or ```File.documentsDirectory``` they all work.

# Tutorials
[How to embed ANEs into **FlashBuilder**, **FlashCC** and **FlashDevelop**](https://www.youtube.com/watch?v=Oubsb_3F3ec&list=PL_mmSjScdnxnSDTMYb1iDX4LemhIJrt1O)  

# Changelog
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

*Nov 03, 2015 - V1.9:*
* doitflash devs merged into MyFLashLab Team.

*May 01, 2013 - V1.0:*
* beginning of the journey!