1. To download the iOS dependency, it is necessary to have cocoapods installed. To install it, follow <a target="_blank" rel="nofollow" href="https://guides.cocoapods.org/using/getting-started.html#toc_3">this guide</a>

2. Add the plugin to the project with the following command

```bash
phonegap plugin add cordova-plugin-emma-sdk --save
```

3. In www/js/index.js add the following code

```javascript
$(document).on("deviceready", function() {
  var config = {
    sessionKey: "%%%SESSION_KEY%%%"
  };

  window.plugins.EMMA.startSession(config);
});
```
