1. If you do not have cocapods integrated in your app, follow <a target="_blank" rel="nofollow" href="https://guides.cocoapods.org/using/getting-started.html#toc_3">this guide</a>

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
       configuration.sessionKey = "%%%SESSION_KEY%%%"

       EMMA.startSession(with: configuration)

       return true
   }
   ```
