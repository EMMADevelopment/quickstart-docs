1. To download the iOS dependency, it is necessary to have cocoapods installed. To install it, follow [this guide](https://guides.cocoapods.org/using/getting-started.html#toc_3)

2. Add the plugin to the project with the following command

	```bash 
	$ cordova plugin add cordova-plugin-emma-sdk --save
	```
	
3. In www/js/index.js add the following code

	```javascript
	var app = {
	    
	    onDeviceReady: function() {
	        app.receivedEvent('deviceready');
	        
	        var config = {
	            sessionKey: 'example0ikl98'
	        };
	        
	        window.plugins.EMMA.startSession(config);
	    }
	};
		
	```
