1. If you do not have cocapods integrate in your app follow [this guide](https://guides.cocoapods.org/using/getting-started.html#toc_3)
2. Add EMMA dependeny to you Podfile file

	```ruby
	pod 'eMMa'
	```
3. To download and install the dependency execute the following command in the terminal

	```
	$ pod install
	```
4. Import the SDK in your AppDelegate and start session in EMMA

	```objective-c 
	#import <EMMA_iOS/EMMA_iOS.h>

	@implementation AppDelegate

	- (BOOL)application:(UIApplication *)application
		didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    
	    EMMAConfiguration * configuration = [EMMAConfiguration new];
	    [configuration setSessionKey:@"example0ikl98"];
	    
	    [EMMA startSessionWithConfiguration:configuration];
    
	}
	@end
		
	```