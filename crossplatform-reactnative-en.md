1. To download the iOS dependency, it is necessary to have cocoapods installed. To install it, follow <a target="_blank" rel="nofollow" href="https://guides.cocoapods.org/using/getting-started.html#toc_3">this guide</a>

2. Add the plugin to the project with the following command

```bash
yarn add emma-react-native-sdk
```
or

```bash
npm install emma-react-native-sdk
```

3. In App.txs add the following code

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