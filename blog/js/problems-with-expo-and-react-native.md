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

**Solution (Usually!)**<br />
Clear the cache when starting expo:<br />
expo start -c  


