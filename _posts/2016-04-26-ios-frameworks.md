---
layout: post
title: iOS公开的Frameworks列表
date: 2016-04-26 09:37:00
category: "iOS"
---

iOS公开的frameworks有哪些，你能一一列举出来吗？你可能告诉我看这个[iOS Frameworks](https://developer.apple.com/library/ios/documentation/Miscellaneous/Conceptual/iPhoneOSTechOverview/iPhoneOSFrameworks/iPhoneOSFrameworks.html#//apple_ref/doc/uid/TP40007898-CH6-SW3), 可是好像不全。So,我们想想别的办法。
执行如下命令（以iOS9.3为例：

{% highlight shell %}
$ cd /Applications/Xcode.app/Contents/Developer/Platforms/iPhoneOS.platform/Developer/SDKs/iPhoneOS9.3.sdk/System/Library/Frameworks
$ ls -1
{% endhighlight %}

输出如下：

{% highlight shell %}
AVFoundation.framework
AVKit.framework
Accelerate.framework
Accounts.framework
AdSupport.framework
AddressBook.framework
AddressBookUI.framework
AssetsLibrary.framework
AudioToolbox.framework
AudioUnit.framework
CFNetwork.framework
CloudKit.framework
Contacts.framework
ContactsUI.framework
CoreAudio.framework
CoreAudioKit.framework
CoreBluetooth.framework
CoreData.framework
CoreFoundation.framework
CoreGraphics.framework
CoreImage.framework
CoreLocation.framework
CoreMIDI.framework
CoreMedia.framework
CoreMotion.framework
CoreSpotlight.framework
CoreTelephony.framework
CoreText.framework
CoreVideo.framework
EventKit.framework
EventKitUI.framework
ExternalAccessory.framework
Foundation.framework
GLKit.framework
GSS.framework
GameController.framework
GameKit.framework
GameplayKit.framework
HealthKit.framework
HealthKitUI.framework
HomeKit.framework
IOKit.framework
ImageIO.framework
JavaScriptCore.framework
LocalAuthentication.framework
MapKit.framework
MediaAccessibility.framework
MediaPlayer.framework
MediaToolbox.framework
MessageUI.framework
Metal.framework
MetalKit.framework
MetalPerformanceShaders.framework
MobileCoreServices.framework
ModelIO.framework
MultipeerConnectivity.framework
NetworkExtension.framework
NewsstandKit.framework
NotificationCenter.framework
OpenAL.framework
OpenGLES.framework
PassKit.framework
Photos.framework
PhotosUI.framework
PushKit.framework
QuartzCore.framework
QuickLook.framework
ReplayKit.framework
SafariServices.framework
SceneKit.framework
Security.framework
Social.framework
SpriteKit.framework
StoreKit.framework
SystemConfiguration.framework
Twitter.framework
UIKit.framework
VideoToolbox.framework
WatchConnectivity.framework
WatchKit.framework
WebKit.framework
iAd.framework
{% endhighlight %}
