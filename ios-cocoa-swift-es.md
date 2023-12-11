1. Si no tienes cocoapods integrado en tu app, sigue <a target="_blank" rel="nofollow" href="https://guides.cocoapods.org/using/getting-started.html#toc_3">esta guía</a>

2. Integra la dependencia de EMMA en el fichero Podfile de la app

   ```ruby
   pod 'eMMa'
   ```

3. Para descargar e instalar la dependencia ejecuta el siguiente comando en el terminal

   ```bash
   pod install
   ```

4. Importa el SDK en tu AppDelegate e inicia sesión en EMMA

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
