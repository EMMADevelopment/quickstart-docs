1.  Dowload the library in .dll format <a target="_blank" rel="nofollow" href="https://github.com/eMMaDevelopment/eMMa-Xamarin-SDK">here</a>

2.  For Android, add as reference the library EMMAAndroidBindings.dll and its dependency InstallReferrer.dll. For iOS, add the library EMMAiOSBindings.dll as reference

3.  For Android, add the following dependencies for the proper functioning of the library

        Kwon.Squareup.OkHttp3.Logging-interceptor (3.9.1.1)
        Kwon.Squareup.Retrofit2.Retrofit-converter (2.3.0.1)
        Karamunting.Xamarin.BumpTech.Glide (v4.8.0)
        Xamarin.Firebase.Messaging (60.1142.1) (Optional)

4.  In your Android project, import the SDK in your Application class and start session in EMMA

    ```c#
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

5.  In your iOS project, import the SDK in your AppDelegate class and start session in EMMA

    ```c#
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
