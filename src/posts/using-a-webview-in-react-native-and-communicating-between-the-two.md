---
layout: layouts/post.njk
title: Using a webview in react-native and communicating between the two
metaTitle: Using a webview in react-native and communicating between the two
metaDesc: >-
  How to display a webview in react-native and handle common use-cases like
  displaying a spinner before the page is loaded and exchanging data between
  both sides
socialImage: images/lynNy7W.png
date: 2020-01-15T11:46:37.671Z
tags:
  - react-native webview inject javascript
---
# Introduction

There are various cases in which you would want to display a Webview in a mobile app. You may want to display your privacy policy that's present in your website, or you may want to integrate with a service that requires the use of a Webview (HelloSign) ...

Whatever is your usecase, you want the best User Experience. So let's dive in and see how we can communicate back and forth between native and a Webview.

First, let's take a look at the official guide for [communicating between js and native](https://github.com/react-native-community/react-native-webview/blob/master/docs/Guide.md#communicating-between-js-and-native). I sum it up below.

tl;dr, There are three ways:

1. React Native -> Web: The `injectedJavaScript` prop:
  1.1. `injectedJavaScript`: This is a script that runs **immediately after the web page loads** for the first time.
  1.2. `injectedJavaScriptBeforeContentLoaded`: This is a script that runs **before the web page loads** for the first time.
The downside of these methods is that they run **only once**
2. React Native -> Web: The `injectJavaScript` method enables you to run some JavaScript in the webpage whenever you want.
3. Web -> React Native: The `postMessage` method and `onMessage` prop
   By setting the `onMessage` prop on the webview, `window.ReactNative.postMessage` method will be injected onto the webview and can be used to send messages 📨 to the native side.

Not yet clear? let's see that in a table

﻿
# Display a loading spinner while the web page is loading
