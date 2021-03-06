# AppAvailability for iOS and Android

A Plugin for Cordova / PhoneGap by [ohh2ahh](http://ohh2ahh.com)

1. [Description](https://github.com/ohh2ahh/AppAvailability#1-description)
2. [Installation](https://github.com/ohh2ahh/AppAvailability#2-installation)
	2. [Automatically (Command-line Interface)](https://github.com/ohh2ahh/AppAvailability#automatically-command-line-interface)
	2. [PhoneGap Build](https://github.com/ohh2ahh/AppAvailability#phonegap-build)
3. [Usage](https://github.com/ohh2ahh/AppAvailability#3-usage)
	3. [iOS](https://github.com/ohh2ahh/AppAvailability#ios)
	3. [Android](https://github.com/ohh2ahh/AppAvailability#android)
4. [Some URI schemes / package names](https://github.com/ohh2ahh/AppAvailability#4-some-uri-schemes--package-names)
5. [License](https://github.com/ohh2ahh/AppAvailability#5-license)

## 1. Description

This plugin allows you to check if an app is installed on the user's device.
It requires an URI scheme (e.g. twitter://) on iOS or a package name (e.g com.twitter.android) on Android.

* Ready for the Command-line Interface of Cordova / PhoneGap 3.0 and later
* Works with PhoneGap Build ([more information](https://build.phonegap.com/plugins/17))

### Supported Platforms

* iOS
* Android

## 2. Installation

The Cordova CLI is the recommended way to install AppAvailability, see [The Command-line Interface](http://cordova.apache.org/docs/en/3.0.0/guide_cli_index.md.html#The%20Command-line%20Interface).

### Automatically (Command-line Interface)
Simply run this command to add AppAvailability to your project:
```
$ cordova plugin add https://github.com/ohh2ahh/AppAvailability.git
```

And if you're using PhoneGap instead of Cordova:
```
$ phonegap local plugin add https://github.com/ohh2ahh/AppAvailability.git
```

### PhoneGap Build

AppAvailability works with PhoneGap build too. You can implement the latest version of the plugin by adding the following xml to your `config.xml`:
```xml
<gap:plugin name="com.ohh2ahh.plugins.appavailability" />
```
Or if you want to use an exact version of AppAvailability:
```xml
<gap:plugin name="com.ohh2ahh.plugins.appavailability" version="0.2.1" />
```

There is no need to reference the JavaScript in your `index.html`.

## 3. Usage

:exclamation: The code changed in version 0.2.0! You can find the [old docs here](https://github.com/ohh2ahh/AppAvailability/blob/v0.1.1/README.md).

### iOS

```javascript
appAvailability.check('twitter://', function(availability) {
    // availability is either true or false
    if(availability) { console.log('Twitter is available'); }
});
```

### Android

```javascript
appAvailability.check('com.twitter.android', function(availability) {
    // availability is either true or false
    if(availability) { console.log('Twitter is available'); }
});
```

## 4. Some URI schemes / package names

[How do I get the URI scheme / package name?](https://github.com/ohh2ahh/AppAvailability/issues/2#issuecomment-22203591)

Twitter:
* iOS: `twitter://` ([more schemes](http://wiki.akosma.com/IPhone_URL_Schemes#Twitter))
* Android: `com.twitter.android`

Facebook:
* iOS: `fb://` (and [many more](http://wiki.akosma.com/IPhone_URL_Schemes#Facebook) as `fb://profile`)
* Android: `com.facebook.katana`

WhatsApp:
* iOS: `whatsapp://` (only since v. 2.10.1, [more information](http://www.whatsapp.com/faq/en/iphone/23559013))
* Android: `com.whatsapp`

## 5. License

[The MIT License (MIT)](http://www.opensource.org/licenses/mit-license.html)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
