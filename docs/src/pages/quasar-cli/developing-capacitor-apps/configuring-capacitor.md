---
title: Configuring Capacitor
desc: How to manage your Capacitor apps with Quasar CLI.
related:
  - /quasar-cli/quasar-conf-js
---

We'll be using Quasar CLI to develop and build a Mobile App. The difference between building a SPA, PWA, Electron App or a Mobile App is simply determined by the "mode" parameter in "quasar dev" and "quasar build" commands.

There are two configuration files of great importance to your mobile apps. We'll go over each one.

## capacitor.config.json
The most important config file for your mobile app is `/src-capacitor/capacitor.config.json`. The `/src-capacitor` folder is a Capacitor project, so please refer to [Capacitor documentation](https://capacitor.ionicframework.com) in order to understand what each file from there does. But for now, have a few moments to read about [capacitor.config.json](https://capacitor.ionicframework.com/docs/basics/configuring-your-app/).

Some properties from this file will get overwritten as we'll see in next section.

## quasar.conf.js
There are two places in `/quasar.conf.js` where you can configure Quasar specific features for Capacitor.

```js
return {
  capacitor: {
    // requires @quasar/app v1.3+
    hideSplashscreen: false // disables auto-hiding the Splashscreen by Quasar CLI
  }
}
```

And you can also configure:

```js
return {
  framework: {
    config: {
      capacitor: {
        iosStatusBarPadding: true/false, // add the dynamic top padding on iOS mobile devices
      }
    }
  }
}
```

Finally, you can also disable or configure the back button hook (used for Dialogs):

```js
return {
  framework: {
    config: {
      capacitor: {
        // Quasar handles app exit on mobile phone back button
        // Requires Quasar v1.9.3+ for true/false, v1.12.6+ for '*' wildcard and array values
        backButtonExit: true/false/'*'/['/login', '/home', '/my-page']
      }
    }
  }
}
```
