1. Add EMMA repository to /app/build.gradle file

	```groovy
	repositories {
	    maven { url 'https://repo.emma.io/emma' }
	} 
	```

2. In that same file, add the EMMA dependency in dependencies section

	```groovy
	dependencies {
	    implementation 'io.emma:eMMaSDK:4.5.+'  
	}
	```

3. Import the SDK in your Application class and start session in EMMA

	```java
	import io.emma.android.EMMA;
		
	public class MyApplication extends Application {
		
	    @Override
	    public void onCreate() {
	        super.onCreate();
		
	        EMMA.Configuration configuration = new EMMA.Configuration.Builder(this)
	            .setSessionKey("%%%SESSION_KEY%%%")
	            .build();
		
	        EMMA.getInstance().startSession(configuration);
	    }
	}
	```
