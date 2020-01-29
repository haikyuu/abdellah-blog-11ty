---
layout: layouts/post.njk
title: Handling form errors - Great UX for your users
date: 2020-01-29T10:27:38.708Z
tags:
  - html
---
In order to provide the best user experience for your users, you need to make the most tedious parts of your app feel good. And the most tedious thing is form filling.

The first UX one thinks of is to display errors after the users clicks on submit. But we want the user to have immediate feedback, which helps a lot in longer forms.  How do we do that in a React application? How do we know an input has been visited and that we can display errors?

## Blur

> The blur event is fired when an element has lost focus. The main difference between this event and focusout is that only the latter bubbles.

### bubbles?

There are two types of event propagation: bubbling and capturing. Let's see that in a diagram (made with excalidraw ✨)

![event propagation](images/excalidraw-2020129113118.png "bubbling vs capturing")
