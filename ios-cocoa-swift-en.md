1. If you do not have cocapods integrated in your app, follow [this guide](https://guides.cocoapods.org/using/getting-started.html#toc_3)
2. Add EMMA dependency to you Podfile file

	```ruby
	pod 'eMMa'
	```
3. To download and install the dependency execute the following command in the terminal

	```
	$ pod install
	```
4. Import the SDK in your AppDelegate and start session in EMMA

	```swift 
	import EMMA_iOS
		
	@UIApplicationMain
	class AppDelegate: UIResponder, UIApplicationDelegate {
		
	func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
	
        let configuration = EMMAConfiguration()
        configuration.sessionKey = "example0ikl98"
    
        EMMA.startSession(with: configuration)
   
        return true
	}
	```