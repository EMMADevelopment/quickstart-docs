1. Para descargar la dependencia de iOS es necesario tener cocoapods instalado. Para instalarlo sigue [esta guía](https://guides.cocoapods.org/using/getting-started.html#toc_3)

2. Añade el plugin al proyecto con el siguiente comando

	```bash 
	$ phonegap plugin add cordova-plugin-emma-sdk --save
	```
	
3. En el www/js/index.js añade el siguiente código

	```javascript
	$(document).on('deviceready', function () {
	    var config = {
	        sessionKey: 'example0ikl98'
	    };
	    
        window.plugins.EMMA.startSession(config);
    });
	```