1. Para descargar la dependencia de iOS es necesario tener cocoapods instalado. Para instalarlo sigue [esta guía](https://guides.cocoapods.org/using/getting-started.html#toc_3)

2. Añade el plugin al proyecto con el siguiente comando

	```bash 
	$ ionic cordova plugin add cordova-plugin-emma-sdk --save
	```
	
3. En el src/app/app.component.ts añade el siguiente código

	```typescript
	declare var window: any;
	
	@Component({
	  selector: 'app-root',
	  templateUrl: 'app.component.html'
	})
	export class AppComponent {
	  constructor(
	    private platform: Platform,
	    private splashScreen: SplashScreen,
	    private statusBar: StatusBar
	  ) {
	    this.platform.ready().then(() => {
	    
	      const EMMA = window.plugins.EMMA;
	
	      const configuration = {
	        sessionKey: 'example0ikl98',
	      };
	
	      EMMA.startSession(configuration);
	
	      this.statusBar.styleDefault();
	      this.splashScreen.hide();
	    });
	  }
	}
	```