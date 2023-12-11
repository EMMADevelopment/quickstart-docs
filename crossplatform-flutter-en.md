1. To download the iOS dependency, it is necessary to have cocoapods installed. To install it, follow <a target="_blank" rel="nofollow" href="https://guides.cocoapods.org/using/getting-started.html#toc_3">this guide</a>

2. Añade la librería al proyecto con el siguiente comando

```bash
flutter pub add emma_flutter_sdk
```

3. In lib/main.dart add the following code

```dart
import 'dart:async';
import 'dart:io' show Platform;

import 'package:emma_flutter_sdk/emma_flutter_sdk.dart';
import 'package:flutter/material.dart';
import 'package:flutter/services.dart';

void main() {
    runApp(MyApp());
}

class MyApp extends StatefulWidget {
    @override
    _MyAppState createState() => _MyAppState();
    }

    class _MyAppState extends State<MyApp> {

    @override
    void initState() {
        super.initState();
        initPlatformState();
        initEMMA()

        await EmmaFlutterSdk.shared
            .startSession("%%%SESSION_KEY%%%", debugEnabled: true);
    }
}
```