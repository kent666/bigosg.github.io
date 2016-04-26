---
layout: post
title: iOS公开的Frameworks列表
date: 2016-04-26 09:37:00
category: "iOS"
---

iOS公开的frameworks有哪些，你能一一列举出来吗？你可能告诉我看这个[iOS Frameworks](https://developer.apple.com/library/ios/documentation/Miscellaneous/Conceptual/iPhoneOSTechOverview/iPhoneOSFrameworks/iPhoneOSFrameworks.html#//apple_ref/doc/uid/TP40007898-CH6-SW3), 可是好像不全。So,我们想想别的办法。
执行如下命令（以iOS9.3为例）：

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

接下来我们按照[iOS Architecture](https://developer.apple.com/library/ios/documentation/Miscellaneous/Conceptual/iPhoneOSTechOverview/Introduction/Introduction.html#//apple_ref/doc/uid/TP40007898-CH1-SW1) 分类整理一遍:

- Cocoa Touch Layer
{% highlight shell %}
AddressBookUI.framework (2.0)
ContactsUI.framework (9.0)
EventKitUI.framework(4.0)
GameKit.framework (3.0)
HealthKitUI.framework (9.3)
iAd.framework (4.0)
MapKit.framework (3.0)
MessageUI.framework (3.0)
NotificationCenter.framework (8.0)
PushKit.framework (8.0)
Twitter.framework (5.0)
UIKit.framework (2.0)
WatchKit.framework (8.2)
{% endhighlight %}

- Media Layer
{% highlight shell %}
AssetsLibrary.framework (4.0)
AVFoundation.framework (2.2)
AVKit.framework (8.0)
VideoToolbox.framework(8.0) (Contains interfaces used by the device. Do not include this framework directly.)
CoreAudio.framework (2.0)
AudioToolbox.framework (2.0)
AudioUnit.framework (2.0)
CoreMIDI.framework (S4.2)
MediaToolbox.framework (6.0)
CoreAudioKit.framework (8.0)
CoreGraphics.framework (2.0)
CoreImage.framework (5.0)
CoreSpotlight.framework (9.0)
CoreText.framework (3.2)
CoreVideo.framework (4.0)
GameController.framework (7.0)
GameplayKit.framework (9.0)
GLKit.framework (5.0)
ImageIO.framework (4.0)
MediaAccessibility.framework (7.0)
MediaPlayer.framework (2.0)
Metal.framework (8.0)
MetalKit.framework (iOS9.0)
MetalPerformanceShaders.framework (9.0)
ModelIO.framework (9.0)
OpenAL.framework (2.0)
OpenGLES.framework (2.0)
Photos.framework (8.0)
PhotosUI.framework (8.0)
QuartzCore.framework (2.0)
ReplayKit.framework (9.0)
SceneKit.framework (8.0)
SpriteKit.framework (7.0)
{% endhighlight %}

- Core Services Layer
{% highlight shell %}
Accounts.framework (5.0)
AddressBook.framework (2.0)
Contacts.framework (9.0)
AdSupport.framework (6.0)
CFNetwork.framework (2.0)
CloudKit.framework (8.0)
CoreAuthentication.framework (8.0)
CoreData.framework (3.0)
CoreFoundation.framework (2.0)
CoreLocation.framework (2.0)
CoreMedia.framework (4.0)
CoreMotion.framework (4.0)
CoreTelephony.framework (4.0)
EventKit.framework (4.0)
Foundation.framework (2.0)
HealthKit.framework (8.0)
HomeKit.framework (8.0)
IOKit.framework (OS X) (Contains interfaces used by the device. Do not use this framework directly.)
JavaScriptCore.framework (7.0)
MobileCoreServices.framework (3.0)
MultipeerConnectivity.framework (7.0)
NewsstandKit.framework (5.0)
PassKit.framework (6.0)
QuickLook.framework (4.0)
SafariServices.framework (7.0)
Social.framework (6.0)
StoreKit.framework (3.0)
SystemConfiguration.framework (2.0)
WatchConnectivity.framework (9.0)
WebKit.framework (8.0)
{% endhighlight %}

- Core OS Layer
{% highlight shell %}
Accelerate.framework (4.0)
CoreBluetooth.framework (5.0)
ExternalAccessory.framework (3.0)
GSS.framework (5.0)
LocalAuthentication.framework (8.0)
NetworkExtension.framework (8.0)
Security.framework (2.0)
{% endhighlight %}

是不是清晰多了，nice!  如果你喜欢最新，请关注[What's New in iOS](https://developer.apple.com/library/ios/releasenotes/General/WhatsNewIniOS/Introduction/Introduction.html#//apple_ref/doc/uid/TP40008244-SW1)。
