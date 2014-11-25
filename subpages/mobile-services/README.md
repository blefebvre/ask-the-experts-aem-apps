# Mobile Services

![Analytics screenshot](../../img/mobile-services-2.png "Analytics screenshot")


## Configure your app

From your app's Command Center, use the 'Metrics' tile to configure your Mobile Services account details:

![Analytics config](../../img/adb_config.png "Analytics config")

Once configured, you will see the tile transform to provide an overview of key metrics tracked by your app (pictured above).


## Testing Analytics with Bloodhound

Testing with Bloodhound currently requires a tweak to `ADBMobileConfig.json`, before uploading to AEM.

From within Bloodhound, located your host details (towards the top left of the app):

![IP address details](../../img/ip.png "IP address details")

Use this host and port to configure the `analytics.server` property value in `ADBMobileConfig.json`

Upload your modified config file to AEM via the 'Metrics' tile, 'Upload AMS SDK Config':

![Config upload](../../img/config-upload.png "Config upload")

Your app is now ready to test. Any interaction with the app will now register as an 'event' in Bloodhound.

[Next →](../phonegap-build)