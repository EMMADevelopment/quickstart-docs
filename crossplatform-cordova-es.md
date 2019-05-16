1. Para descargar la dependencia de iOS es necesario tener cocoapods instalado. Para instalarlo sigue [esta guía](https://guides.cocoapods.org/using/getting-started.html#toc_3)

2. Añade el plugin al proyecto con el siguiente comando

	```bash 
	$ cordova plugin add cordova-plugin-emma-sdk --save
	```
	
3. En el www/js/index.js añade el siguiente código

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