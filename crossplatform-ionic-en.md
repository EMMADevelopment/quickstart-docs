1. To download the iOS dependency, it is necessary to have cocoapods installed. To install it, follow <a target="_blank" rel="nofollow" href="https://guides.cocoapods.org/using/getting-started.html#toc_3">this guide</a>

2. Add the plugin to the project with the following command

```bash
ionic cordova plugin add cordova-plugin-emma-sdk --save
```

3. In src/app/app.component.ts add the following code

```typescript
declare var window: any;

@Component({
  selector: "app-root",
  templateUrl: "app.component.html"
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
        sessionKey: "%%%SESSION_KEY%%%"
      };

      EMMA.startSession(configuration);

      this.statusBar.styleDefault();
      this.splashScreen.hide();
    });
  }
}
```
