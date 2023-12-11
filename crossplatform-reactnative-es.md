1. Para descargar la dependencia de iOS es necesario tener cocoapods instalado. Para instalarlo sigue <a target="_blank" rel="nofollow" href="https://guides.cocoapods.org/using/getting-started.html#toc_3">esta guía</a>

2. Añade el plugin al proyecto con el siguiente comando

```bash
yarn add emma-react-native-sdk
```
o

```bash
npm install emma-react-native-sdk
```

3. En el App.tsx añade el siguiente código

```typescript
import React, { Component } from 'react';
import EmmaSdk from 'emma-react-native-sdk';

EmmaSdk.startSession(
{
    sessionKey: '%%%SESSION_KEY%%%',
    isDebug: false, // Optional, default: false
    queueTime: 10, // Optional, default: 10
    customPowlinkDomains: ['example.com'], // Optional, default: []
    customShortPowlinkDomains: ['ex.co'], // Optional, default: []
    trackScreenEvents: true, // Optional, default: false
},
() => {
    console.log('Got it!');
},
(error) => {
    console.error('Oh, oh!', error);
}
);
```