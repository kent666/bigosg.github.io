---
layout: post
title: iOS系统的Frameworks和Libraries列表
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

{% highlight shell %}
$ cd /Applications/Xcode.app/Contents/Developer/Platforms/iPhoneOS.platform/Developer/SDKs/iPhoneOS9.2.sdk/System/Library/PrivateFrameworks
$ ls -1
{% endhighlight %}

输出如下：

{% highlight shell %}
ABLE.framework
ABLEModel.framework
ACTFramework.framework
AGXCompilerConnection.framework
AGXCompilerCore.framework
AITTarget.framework
AOSKit.framework
AOSNotification.framework
APTransport.framework
ATFoundation.framework
AXRuntime.framework
Accessibility.framework
AccessibilityUtilities.framework
AccountNotification.framework
AccountSettings.framework
AccountsDaemon.framework
AccountsUI.framework
AggregateDictionary.framework
AggregateDictionaryHistory.framework
AirPlayForCarDisplaySim.framework
AirPlayReceiver.framework
AirPlaySender.framework
AirPlaySupport.framework
AirPortAssistant.framework
AirTraffic.framework
AirTrafficDevice.framework
AnnotationKit.framework
AppConduit.framework
AppLaunchStats.framework
AppStoreUI.framework
AppSupport.framework
AppleAccount.framework
AppleAccountUI.framework
AppleBasebandManager.framework
AppleBasebandServices.framework
AppleFSCompression.framework
AppleIDAuthSupport.framework
AppleIDSSOAuthentication.framework
AppleJPEG.framework
AppleLDAP.framework
ApplePDPHelper.framework
ApplePushService.framework
AppleSRP.framework
AppleSauce.framework
AppleSerialMultiplexer.framework
AppleVXD375Framework.framework
AppleVXD390Framework.framework
AskPermission.framework
AssertionServices.framework
AssetCacheServices.framework
AssetsLibraryServices.framework
AssistantServices.framework
AuthKit.framework
AuthKitUI.framework
BTLEAudioController.framework
BackBoardServices.framework
BackgroundTaskAgent.framework
BaseBoard.framework
BaseBoardUI.framework
BatteryCenter.framework
BiometricKit.framework
BiometricKitUI.framework
BluetoothManager.framework
Bom.framework
BookmarkDAV.framework
BridgePreferences.framework
BulletinBoard.framework
BulletinDistributorCompanion.framework
CPMLBestShim.framework
CacheDelete.framework
CalDAV.framework
Calculate.framework
CalendarDaemon.framework
CalendarDatabase.framework
CalendarFoundation.framework
CalendarUIKit.framework
CallHistory.framework
CameraKit.framework
CameraUI.framework
CaptiveNetwork.framework
CarKit.framework
Celestial.framework
CellularPlanManager.framework
CertInfo.framework
CertUI.framework
CharlieKit.framework
ChatKit.framework
ChunkingLibrary.framework
CloudDocs.framework
CloudDocsDaemon.framework
CloudKitDaemon.framework
CloudPhotoLibrary.framework
CloudServices.framework
ColorSync.framework
CommonAuth.framework
CommonUtilities.framework
CommunicationsFilter.framework
CommunicationsSetupUI.framework
CompanionCamera.framework
CompanionFindMy.framework
CompanionSync.framework
CompassUI.framework
Conference.framework
ConstantClasses.framework
ContactsAutocomplete.framework
ContactsFoundation.framework
ContentIndex.framework
CoreAUC.framework
CoreActivity.framework
CoreBrightness.framework
CoreCDP.framework
CoreCDPInternal.framework
CoreCDPUI.framework
CoreCapture.framework
CoreCaptureControl.framework
CoreCaptureDaemon.framework
CoreDAV.framework
CoreDuet.framework
CoreDuetDaemonProtocol.framework
CoreDuetDataModel.framework
CoreDuetDebugLogging.framework
CoreDuetStatistics.framework
CoreFollowUp.framework
CoreFollowUpUI.framework
CoreHAP.framework
CoreHandwriting.framework
CoreMediaStream.framework
CoreMotionCommon.framework
CoreNLP.framework
CoreOptimization.framework
CorePDF.framework
CorePrediction.framework
CoreRC.framework
CoreRecents.framework
CoreRecognition.framework
CoreRoutine.framework
CoreSDB.framework
CoreServicesInternal.framework
CoreSuggestions.framework
CoreSuggestionsInternals.framework
CoreSymbolication.framework
CoreTelephonyBypass.framework
CoreThemeDefinition.framework
CoreTime.framework
CoreUI.framework
CoreUtils.framework
CrashReporterSupport.framework
Crucible.framework
CryptoTokenKit.framework
DAAPKit.framework
DCIMServices.framework
DataAccess.framework
DataAccessExpress.framework
DataAccessUI.framework
DataDetectorsCore.framework
DataDetectorsNaturalLanguage.framework
DataDetectorsUI.framework
DataMigration.framework
DeviceOMatic.framework
DeviceToDeviceManager.framework
DiagnosticExtensions.framework
DiagnosticLogCollection.framework
DictionaryServices.framework
DiskSpaceDiagnostics.framework
Duet.framework
DuetExpertCenter.framework
DuetPLLConfigLogger.framework
DuetRecommendation.framework
EAFirmwareUpdater.framework
EAP8021X.framework
ETPeople.framework
EasyConfig.framework
EmbeddedAcousticRecognition.framework
FMCore.framework
FMCoreLite.framework
FMCoreUI.framework
FMF.framework
FMFUI.framework
FTAWD.framework
FTClientServices.framework
FTServices.framework
FaceCore.framework
FamilyCircle.framework
FamilyNotification.framework
FileProvider.framework
FindMyDevice.framework
FindMyDeviceUI.framework
FitnessUI.framework
FlightRecorder.framework
FlightUtilities.framework
FontServices.framework
FoundationODR.framework
FrontBoard.framework
FrontBoardServices.framework
FuseUI.framework
Futhark.framework
GPUCompiler.framework
GPUSupport.framework
GameCenter.framework
GameCenterFoundation.framework
GameCenterPrivateUI.framework
GameCenterUI.framework
GameKitServices.framework
GenerationalStorage.framework
GeoServices.framework
GraphicsServices.framework
H6ISPServices.framework
HSAAuthentication.framework
HangTracer.framework
HealthDaemon.framework
HealthKitExtensions.framework
HealthKitUI.framework
Heimdal.framework
HelpKit.framework
HomeKitDaemon.framework
HomeSharing.framework
IAP.framework
IAPAuthentication.framework
IDS.framework
IDSFoundation.framework
IMAVCore.framework
IMCore.framework
IMDMessageServices.framework
IMDPersistence.framework
IMDaemonCore.framework
IMFoundation.framework
IMTranscoding.framework
IMTransferServices.framework
IOAccelMemoryInfo.framework
IOAccelerator.framework
IOMobileFramebuffer.framework
IOSurface.framework
IOSurfaceAccelerator.framework
IPTelephony.framework
ITMLKit.framework
ImageCapture.framework
IncomingCallFilter.framework
InternalPreferences.framework
InternationalTextSearch.framework
IntlPreferences.framework
JavaScriptCore.framework
Jet.framework
KeyboardArbiter.framework
LanguageModeling.framework
LatentSemanticMapping.framework
LegacyGameKit.framework
MIME.framework
MMCS.framework
MMCSServices.framework
MPUFoundation.framework
MTLCompiler.framework
MailServices.framework
ManagedConfiguration.framework
MapsSupport.framework
Marco.framework
MarkupUI.framework
MediaControlSender.framework
MediaLibrary.framework
MediaLibraryCore.framework
MediaPlatform.framework
MediaPlayerUI.framework
MediaRemote.framework
MediaServices.framework
MediaSocial.framework
MediaStream.framework
Message.framework
MessageProtection.framework
MessageSupport.framework
MetalTools.framework
MobileAccessoryUpdater.framework
MobileActivation.framework
MobileAsset.framework
MobileAssetUpdater.framework
MobileBackup.framework
MobileBluetooth.framework
MobileContainerManager.framework
MobileDelete.framework
MobileDeviceLink.framework
MobileIcons.framework
MobileInstallation.framework
MobileKeyBag.framework
MobileLookup.framework
MobileObliteration.framework
MobileSoftwareUpdate.framework
MobileSpotlightIndex.framework
MobileStorage.framework
MobileSync.framework
MobileSystemServices.framework
MobileTimer.framework
MobileWiFi.framework
MultitouchSupport.framework
MusicCarDisplayUI.framework
MusicLibrary.framework
MusicStoreUI.framework
NCLaunchStats.framework
NanoAppRegistry.framework
NanoAudioControl.framework
NanoBackup.framework
NanoComplicationSettings.framework
NanoGlanceSettings.framework
NanoLeash.framework
NanoMailKitServer.framework
NanoMediaRemote.framework
NanoMusicSync.framework
NanoPassKit.framework
NanoPhonePerfTesting.framework
NanoPreferencesSync.framework
NanoRegistry.framework
NanoResourceGrabber.framework
NanoSetupUISupport.framework
NanoSystemSettings.framework
NanoTimeKitCompanion.framework
NetAppsUtilitiesUI.framework
Netrb.framework
Network.framework
NetworkStatistics.framework
Notes.framework
NotesShared.framework
NotificationsUI.framework
OAuth.framework
OfficeImport.framework
OpenCL.framework
PBBridgeSupport.framework
PacketFilter.framework
PairedSync.framework
PairedUnlock.framework
Parsec.framework
ParsecSubscriptionServiceSupport.framework
PassKitCore.framework
Pegasus.framework
PerformanceAnalysis.framework
PersistentConnection.framework
PhotoBoothEffects.framework
PhotoEditSupport.framework
PhotoLibrary.framework
PhotoLibraryServices.framework
PhotosFormats.framework
PhotosPlayer.framework
PhysicsKit.framework
PlugInKit.framework
PowerLog.framework
PowerlogAccounting.framework
PowerlogControl.framework
PowerlogCore.framework
PowerlogDatabaseReader.framework
PowerlogFullOperators.framework
PowerlogHelperdOperators.framework
PowerlogLiteOperators.framework
Preferences.framework
PreferencesUI.framework
PrintKit.framework
ProgressUI.framework
ProofReader.framework
ProtectedCloudStorage.framework
ProtocolBuffer.framework
ProxiedCrashCopierClient.framework
Quagga.framework
QuickLookThumbnailing.framework
RTCReporting.framework
RadioUI.framework
RemindersUI.framework
RemoteMediaServices.framework
RemoteUI.framework
ResponseKit.framework
SAObjects.framework
SDAPI.framework
SafariSafeBrowsing.framework
SafariShared.framework
ScreenReaderBrailleDriver.framework
ScreenReaderCore.framework
ScreenReaderOutput.framework
ScreenReaderOutputServer.framework
Search.framework
SearchUI.framework
ServerAccounts.framework
ServerDocsProtocol.framework
ServiceManagement.framework
SetupAssistant.framework
SetupAssistantUI.framework
SharedWebCredentials.framework
Sharing.framework
SiriTasks.framework
SiriUICore.framework
SlideshowKit.framework
SoftwareBehaviorServices.framework
SoftwareUpdateBridge.framework
SoftwareUpdateServices.framework
Speech.framework
SplashBoard.framework
Spotlight.framework
SpotlightDaemon.framework
SpotlightReceiver.framework
SpotlightUI.framework
SpringBoardFoundation.framework
SpringBoardServices.framework
SpringBoardUI.framework
SpringBoardUIServices.framework
Stocks.framework
StoreBookkeeper.framework
StoreBookkeeperClient.framework
StoreKitUI.framework
StoreServices.framework
StoreServicesCore.framework
StreamingZip.framework
Symbolication.framework
Symptoms.framework
SyncedDefaults.framework
TCC.framework
TSReading.framework
TSUtility.framework
TelephonyRPC.framework
TelephonyUI.framework
TelephonyUtilities.framework
TelephonyXPCClient.framework
TelephonyXPCServer.framework
TextInput.framework
TextToSpeech.framework
ThermalMonitorExporter.framework
Tips.framework
ToneKit.framework
ToneLibrary.framework
TouchRemote.framework
UIAccessibility.framework
UIFoundation.framework
UITriggerVC.framework
UserActivity.framework
UserFS.framework
UserNotification.framework
UserNotificationServices.framework
VPNUtilities.framework
VUSocialUpload.framework
VectorKit.framework
VideoProcessing.framework
VideoUpload.framework
VisualAlert.framework
VisualVoicemail.framework
VoiceMemos.framework
VoiceServices.framework
VoiceTrigger.framework
VoiceTriggerUI.framework
VoicemailStore.framework
Weather.framework
WeatherUI.framework
WebApp.framework
WebBookmarks.framework
WebContentAnalysis.framework
WebCore.framework
WebInspector.framework
WebKit.framework
WebKitLegacy.framework
WebUI.framework
WelcomeKit.framework
WelcomeKitCore.framework
WelcomeKitUI.framework
WiFiCloudSyncEngine.framework
WiFiLogCapture.framework
WirelessCoexManager.framework
WirelessDiagnostics.framework
WirelessProximity.framework
XPCKit.framework
XPCService.framework
YouTube.framework
iAdCore.framework
iAdDeveloper.framework
iAdServices.framework
iCalendar.framework
iCloudNotification.framework
iOSDiagnostics.framework
iOSDiagnosticsSupport.framework
iPhotoMigrationSupport.framework
iTunesStore.framework
iTunesStoreUI.framework
iWorkImport.framework
kperf.framework
kperfdata.framework
oncrpc.framework
vCard.framework
{% endhighlight %}
