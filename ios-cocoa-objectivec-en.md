1. If you do not have cocapods integrate in your app follow <a target="_blank" rel="nofollow" href="https://guides.cocoapods.org/using/getting-started.html#toc_3">this guide</a>

2. Add EMMA dependeny to you Podfile file

```bash
pod 'eMMa'
```

3. To download and install the dependency execute the following command in the terminal

```bash
pod install
```

4. Import the SDK in your AppDelegate and start session in EMMA

```objectivec
#import <EMMA_iOS/EMMA_iOS.h>

@implementation AppDelegate

- (BOOL)application:(UIApplication *)application
   didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {

      EMMAConfiguration * configuration = [EMMAConfiguration new];
      [configuration setSessionKey:@"%%%SESSION_KEY%%%"];

      [EMMA startSessionWithConfiguration:configuration];

}
@end

```
