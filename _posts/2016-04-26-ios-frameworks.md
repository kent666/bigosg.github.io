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

### Cocoa Touch Layer
- High-Level Features
  - App Extensions
  - Handoff
  - Document Picker
  - AirDrop
  - TextKit
  - UIKit Dynamics
  - Multitasking
  - Auto Layout
  - Storyboards
  - UI State Preservation
  - Apple Push Notification Service
  - Local Notifications
  - Gesture Recognizers
  - Standard System View Controllers
    - View Controller Programming Guide for iOS
    - View Controller Catalog for iOS
- Cocoa Touch Frameworks
  - AddressBookUI.framework (iOS2.0)
  - ContactsUI.framework (iOS9.0)
  - EventKitUI.framework (iOS4.0)
  - GameKit.framework (iOS3.0)
  - iAd.framework (iOS4.0)
  - MapKit.framework (iOS3.0)
  - MessageUI.framework (iOS3.0)
  - NotificationCenter.framework (iOS8.0)
  - PushKit.framework (iOS8.0)
  - Twitter.framework (iOS5.0)
  - UIKit.framework (iOS2.0)
  - WatchKit.framework (iOS8.2)

### Media Layer
- Graphics Technologies
- Audio Technologies
- Video Technologies
- AirPlay
- Media Layer Frameworks
  - AssetsLibrary.framework (iOS4.0)
  - AVFoundation.framework (iOS2.2)
  - AVKit.framework (iOS8.0)
  - VideoToolbox.framework(iOS8.0) (Contains interfaces used by the device. Do not include this framework directly.)
  - CoreAudio.framework (iOS2.0)
  - AudioToolbox.framework (iOS2.0)
  - AudioUnit.framework (iOS2.0)
  - CoreMIDI.framework (iOS4.2)
  - MediaToolbox.framework (iOS6.0)
  - CoreAudioKit.framework (iOS8.0)
  - CoreGraphics.framework (iOS2.0)
  - CoreImage.framework (iOS5.0)
  - CoreSpotlight.framework (iOS9.0)
  - CoreText.framework (iOS3.2)
  - CoreVideo.framework (iOS4.0)
  - GameController.framework (iOS7.0)
  - GameplayKit.framework (iOS9.0)
  - GLKit.framework (iOS5.0)
  - ImageIO.framework (iOS4.0)
  - MediaAccessibility.framework (iOS7.0)
  - MediaPlayer.framework (iOS2.0)
  - Metal.framework (iOS8.0)
  - MetalKit.framework (iOS9.0)
  - MetalPerformanceShaders.framework (iOS9.0)
  - ModelIO.framework (iOS9.0)
  - OpenAL.framework (iOS2.0)
  - OpenGLES.framework (iOS2.0)
  - Photos.framework (iOS8.0)
  - PhotosUI.framework (iOS8.0)
  - QuartzCore.framework (iOS2.0)
  - ReplayKit.framework (iOS9.0)
  - SceneKit.framework (iOS8.0)
  - SpriteKit.framework (iOS7.0)

### Core Services Layer
- High-Level Features
  - Peer-to-Peer Services
  - iCloud Storage
  - Block Objects
  - Data Protection
  - File-Sharing Support
  - Grand Central Dispatch
  - In-App Purchase
  - SQLite
  - XML Support
- Core Services Frameworks
  - Accounts.framework (iOS5.0)
  - AddressBook.framework (iOS2.0)
  - Contacts.framework (iOS9.0)
  - AdSupport.framework (iOS6.0)
  - CFNetwork.framework (iOS2.0)
  - CloudKit.framework (iOS8.0)
  - CoreAuthentication.framework(iOS 8.0)
  - CoreData.framework (iOS3.0)
  - CoreFoundation.framework (iOS2.0)
    - <http://limboy.me/ios/2013/06/07/core-foundation.html>
    - <http://stackoverflow.com/questions/9353804/cf-objects-vs-ns-objects>
    - <http://stackoverflow.com/questions/11436501/what-is-the-purpose-of-the-corefoundation-framework>
    - <http://stackoverflow.com/questions/1843251/difference-between-foundation-framework-and-core-foundation-framework>
  - CoreLocation.framework (iOS2.0)
  - CoreMedia.framework (iOS4.0)
  - CoreMotion.framework (iOS4.0)
  - CoreTelephony.framework (iOS4.0)
  - EventKit.framework (iOS4.0)
  - Foundation.framework (iOS2.0)
  - HealthKit.framework (iOS8.0)
  - HomeKit.framework (iOS8.0)
  - IOKit.framework (OS X) (Contains interfaces used by the device. Do not use this framework directly.)
  - JavaScriptCore.framework (iOS7.0)
  - MobileCoreServices.framework (iOS3.0)
  - MultipeerConnectivity.framework (iOS7.0)
  - NewsstandKit.framework (iOS5.0)
  - PassKit.framework (iOS6.0)
  - QuickLook.framework (iOS4.0)
  - SafariServices.framework (iOS7.0)
  - Social.framework (iOS6.0)
  - StoreKit.framework (iOS3.0)
  - SystemConfiguration.framework (iOS2.0)
  - WatchConnectivity.framework (iOS9.0)
  - WebKit.framework (iOS8.0)

### Core OS Layer
- Frameworks
  - Accelerate.framework (iOS4.0)
  - CoreBluetooth.framework (iOS5.0)
  - ExternalAccessory.framework (iOS3.0)
  - GSS.framework (iOS5.0)
  - LocalAuthentication.framework (iOS8.0)
  - NetworkExtension.framework (iOS8.0)
  - Security.framework (iOS2.0)
- System
  - Concurrency (POSIX threads and Grand Central Dispatch)
  - Networking (BSD sockets)
  - File-system access
  - Standard I/O
  - Bonjour and DNS services
  - Locale information
  - Memory allocation
  - Math computations
- 64-Bit Support

整个iOS系统结构清晰多了，nice!
