# PhoneGap

![PhoneGap logo](../../img/phonegap.png "PhoneGap logo")

Just getting started? Check out [@mwbrooks](https://twitter.com/mwbrooks)'s excellent beginners guide: https://github.com/mwbrooks/phonegap-day-workshop-beginner/wiki

## Slides

http://brucelefebvre.com/slides/mobile-apps-m-and-m-in-aem/#/18

From 'Mobile apps: Made and managed in AEM', originally presented at AEM Hub 2014.

## Demo

With a few simple commands we can have a cross-platform app running on our mobile device. Please refer to the [install instructions](https://github.com/mwbrooks/phonegap-day-workshop-beginner/wiki/phonegap-cli#install) for details on preparing to run the CLI.

Create the app:

	phonegap create ask-the-experts-demo
	cd ask-the-experts-demo/

Run the app, targeting the emulator:

	phonegap run ios --emulator

Try the app on your device (you will need the [PhoneGap developer app](https://github.com/mwbrooks/phonegap-day-workshop-beginner/wiki/phonegap-developer-app) for this):

	phonegap serve
	
## Use a Plugin

Let's make a selfie app. (Why not?)

We'll require use of the device camera. Add the [camera plugin](https://github.com/apache/cordova-plugin-camera):

	phonegap plugin add org.apache.cordova.camera

Open js/index.html and add the following to the `onDeviceReady` function:

```
navigator.camera.getPicture( 
    function success(imageData) {
        document.body.innerHTML = '<h2>Cool selfie</h2>';
        document.body.innerHTML += '<img src="data:image/jpeg;base64,' + imageData + '" style="width:100%"/>';
    }, 
    function error() {
        // NOP
    }, 
    {
        quality: 25,
        destinationType: Camera.DestinationType.DATA_URL
    }
);
```

Save it, and try it out on your device instantly.