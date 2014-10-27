sujuvuusnavigaattori-wrapper
============================

This project is for wrapping the [Sujuvuusnavigaattori](https://github.com/okffi/sujuvuusnavigaattori/) application
inside a native application. [Cordova](http://cordova.apache.org/) also known as PhoneGap is used for this.

## Getting started

It is assumed that you are somewhat familiar with NodeJS and git. You should have them installed before proceeding with these instructions. Also install grunt: `sudo npm install -g grunt-cli`.

1. Cordova can be installed following [Installing the Cordova CLI](http://docs.phonegap.com/en/3.5.0/guide_cli_index.md.html#The%20Command-Line%20Interface_installing_the_cordova_cli) instructions in *The Command-Line Interface* chapter of the PhoneGap API Documentation.
2. After installing Cordova you should open terminal / command line and move to directory where you want the Sujuvuusnavigaattori-wrapper to be put. In the directory where you moved clone the Sujuvuusnavigaattori-wrapper, i.e. run the `git clone` command. Then to clone the Sujuvuusnavigaattori sub project run `cd www`, `git submodule init`, and `git submodule update --remote www`.
3. Now is good time to install platform tools. See [iOS specific](#iOSplat) or [Android specific](#androidplat) help.
4. After platform tools are installed you can run, for example `cordova build ios` or `cordova build android` at the sujuvuusnavigaattori-wrapper root directory. If there was any errors, ask help.

<a name="plathelp" />
##Platform specific help

<a name="iOSplat" />
### iOS Specific help

Cordova has good general [iOS instructions](http://docs.phonegap.com/en/3.5.0/guide_platforms_ios_index.md.html#iOS%20Platform%20Guide), so you should see them. It should be possible to run `cordova build ios` succesfully after following them. However, before creating application archive (.ipa) from Xcode, you should remember:

1. Update the contents of the www directory to the latest version: `git submodule update --remote www`
2. Run 'grunt` in the www directory.
3. Run `cordova build ios` in the project root directory 
4. Delete the node_modules directory from the `sujuvuusnavigaattori-wrapper/platforms/ios/www` directory before opening the project in Xcode for archiving. Otherwise there may be validation error when trying to create archive. 

<a name="androidplat" />
### Android Specific help

Cordova has also [Android instructions](http://docs.phonegap.com/en/3.5.0/guide_platforms_android_index.md.html#Android%20Platform%20Guide). Few notes for installing Android tools for Mac:

1. Install Android Studio
2. Run Android Studio, select Configure -> SDK Manager. Install from Tools: Android SDK Tools, Android SDK Platform-tools, Android SDK Build-tools (19.1 and above). Install from Android 4.4W: SDK Platform. From Android 4.4.2: SDK Platform and Google APIs and Sources fro Android SDK. From Extras: Android Support Repository and Android Support Library. 
3. `export ANDROID_HOME="/Applications/Android Studio.app/sdk"`
4. [Install ant](http://www.nic.funet.fi/pub/mirrors/apache.org//ant/binaries/apache-ant-1.9.4-bin.zip)
5. `export PATH=${PATH}:/Applications/apache-ant-1.9.4/bin`
