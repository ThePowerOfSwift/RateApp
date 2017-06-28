<img src="https://cdn.rawgit.com/IvanVorobei/RateApp/fe2293bd/resources/rate-app%20-%20baner%20-%20outline.svg"/>

## About
This project simplifies the work on the feedback requests. A beautiful dialog box increases the conversion.

<img src="https://cdn.rawgit.com/IvanVorobei/RateApp/fe2293bd/resources/rate-app%20-%20mockup_preview.gif" width="600">

## Requirements
Xcode 8 and Swift 3. Ready for use on iOS 8+

## Integration
Drop in `Sparrow` folder to your Xcode project (make sure to enable "Copy items if needed" and "Create groups").

Or via CocoaPods:
```ruby
pod 'Sparrow/Modules/RateApp', :git => 'https://github.com/IvanVorobei/Sparrow.git’
```
## How to use
Call `SPRateApp` and choose type UI (for example: `dialog/bannerWithIndicator`)
```swift
class ViewController: UIViewController {

    override func viewDidAppear(_ animated: Bool) {
        super.viewDidAppear(animated)
        SPRateApp.dialog.bannerWithIndicator.present(on: self, applicationID: "1241292508")
    }
}
```
If you want to configure time ranges for requesting permissions, you can use project mechanisms
```swift
if SPRateApp.isShowDialog() {
    SPRateApp.dialog.bannerWithIndicator.present(on: self, applicationID: "1241292508")
}
```

If you want to set a custom time frame, use the function:
```swift
SPRateApp.setTimeInterval(days: 3)
```

## Types of presentation
Did you notice that when initialized the `SPRateApp` - we chose the module (`SPRateApp.dialog.bannerWithIndicator...`). You can choose an appropriate visual component. They all adapted to the iPad and iPhone for all screens and for all orientations (currently available `dialog/bannerWithIndicator`, but soon I will add number of presentations)

<img src="https://cdn.rawgit.com/IvanVorobei/RequestPermission/e85814ac/resources/request-permission_presenters.png"/>

## Delegates
To track events associated with `SPRateApp`, implement the protocol `SPRateAppEventsDelegate` and pass the delegate
```swift
SPRateApp.dialog.bannerWithIndicator.present(
    on: self,
    applicationID: "1241292508",
    delegate: self
)
```
## Customize
If you want to change data in a particular module - you should implement a class supporting the protocol. For example, for module `dialog/bannerWithIndicator`, you should implement the protocol `SPRateAppBannerWithIndicatorDataSourceInterface`. Then the class object needs to be passed to creator
```swift
SPRateApp.dialog.bannerWithIndicator.present(
    on: self,
    applicationID: "1241292508",
    dataSource: CustomDataSource()
)
```

## Apps, using SPRateApp
I like the idea to specify applications that use the RequestPermission. Please, contact me via email (you can find it in the section "Contacts") so that I added app here

## License
SPRateApp is released under the MIT license. Check LICENSE.md for details

## Other
<img src="https://cdn.rawgit.com/IvanVorobei/RequestPermission/e85814ac/resources/powered_by_sparrow.svg"/>

In the project you can find my library [Sparrow](https://github.com/IvanVorobei/Sparrow). It's a library, on which the module is written. Unfortunately, to save time in development, I wrote RateApp using this library. Don't worry, within just Swift files and a lot of useful things. Maybe you will like it:)

## Contact
 
[https://hello.ivanvorobei.by](https://hello.ivanvorobei.by)

[https://ivanvorobei.by](https://hello.ivanvorobei.by) 

hello@ivanvorobei.by

## Support
The project is fully free, I do not impose any restrictions on its use. I'm, just like you, want to do useful things. If you have a desire to help, tell friends about the project or [donate](http://ivanvorobei.by/donate). Thanks!
