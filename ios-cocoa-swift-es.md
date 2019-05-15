1. Si no tienes cocoapods integrado en tu app, sigue [esta guía](https://guides.cocoapods.org/using/getting-started.html#toc_3)
2. Integra la dependencia de EMMA en el fichero Podfile de la app

	```ruby
	pod 'eMMa'
	```
3. Para descargar e instalar la dependencia ejecuta el siguiente comando en el terminal

	```
	$ pod install
	```
4. Importa el SDK en tu AppDelegate e inicia sesión en EMMA

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
		