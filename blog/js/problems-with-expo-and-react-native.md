---
date: 2019-12-08
permalink: /blog/js/problems-with-expo-and-react-native
linktitle: Solutions to Various Problems with Expo, React Native, Native Base etc
title: Solutions to Various Problems with Expo and React Native, Native Base etc
weight: 10
---


Simple solutions to compilation breakages and expo falling over etc.

## Error starting Expo:

```
Could not get status from Metro bundler. connect ECONNREFUSED 127.0.0.1:19001
Connecting to Metro bundler failed.
Error: Connecting to Metro bundler failed.
```

#### Solution (Usually!)

Clear the cache when starting expo:<br />
expo start -c  


## TypeError: Cannot read property 'style' of undefined

```
 23 | activeTextColor: PropTypes.string,
 24 | inactiveTextColor: PropTypes.string,
 25 | disabledTextColor: PropTypes.string,
 26 | tabStyle: ViewPropTypes.style,
 27 | renderTab: PropTypes.func,
 28 | underlineStyle: ViewPropTypes.style,
 29 | tabContainerStyle: ViewPropTypes.style,
```

#### Cause
React Native removed ViewPropTypes

#### Solution

Put it back in grrrrrrrrrrr
- Open node_modules/react-native-web/dist/index.js
- Insert this at the bottom of the file:
```
export const ViewPropTypes = { style: null };
```
