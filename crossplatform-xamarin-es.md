1.  Descarga la libreria en formato .dll <a target="_blank" rel="nofollow" href="https://github.com/eMMaDevelopment/eMMa-Xamarin-SDK">aquí</a>

2.  Para Android, añade como referencia al proyecto la librería EMMAAndroidBindings.dll y su dependencia InstallReferrer.dll en el caso de Android. Para iOS añade EMMAiOSBindings.dll

3.  Para Android añade las siguientes dependencias para el correcto funcionamiento de la librería

        Kwon.Squareup.OkHttp3.Logging-interceptor (3.9.1.1)
        Kwon.Squareup.Retrofit2.Retrofit-converter (2.3.0.1)
        Karamunting.Xamarin.BumpTech.Glide (v4.8.0)
        Xamarin.Firebase.Messaging (60.1142.1) (Optional)

4.  En tu proyecto Android, importa el SDK en tu clase Application e inicia sesión en EMMA

```csharp
using EMMASDK;
using EMMASDK.Model;

namespace MyApp.Droid
{
    [Application]
    public class MainApplication : Application
    {
        public MainApplication(IntPtr handle, JniHandleOwnership transer) :base(handle, transer) { }

        public override void OnCreate()
        {
                base.OnCreate();

                EMMA.Configuration configuration = new EMMA.Configuration.Builder(this)
                .SetSessionKey("%%%SESSION_KEY%%%")
                .Build();

                EMMA.Instance.StartSession(configuration);
        }
    }
}
```

5.  En tu proyecto iOS, importa el SDK en tu clase AppDelegate e inicia sesión en EMMA

```csharp
using EMMASDK;

namespace MyApp.iOS
{
    [Register("AppDelegate")]
    public class AppDelegate : UIApplicationDelegate
    {
        public override UIWindow Window
        {
            get;
            set;
        }

        public override bool FinishedLaunching(UIApplication application, NSDictionary launchOptions)
        {

            EMMAConfiguration configuration = new EMMAConfiguration();
            configuration.SessionKey = "%%%SESSION_KEY%%%";

            EMMA.StartSessionWithConfiguration(configuration);
            return true;
        }
    }
}
```
