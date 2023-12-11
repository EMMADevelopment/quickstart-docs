1. Para descargar la dependencia de iOS es necesario tener cocoapods instalado. Para instalarlo sigue <a target="_blank" rel="nofollow" href="https://guides.cocoapods.org/using/getting-started.html#toc_3">esta guía</a>

2. Add the library to the project with the following command

```bash
flutter pub add emma_flutter_sdk
```

3. En el lib/main.dart añade el siguiente código

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