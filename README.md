<h2>Deploy Angular 6.0 (HTML, JS, CSS) App to cross platform mobile, web and desktop using Ionic Capacitor</h2>

<h4>Objective:</h4>

The development environment setup in this episode will further be utilized in multiple desktop, web and mobile apps development in near future.<br>

[Click here for Video Tutorials !](https://www.youtube.com/watch?v=Tua9Cbw_YgU&list=PLp0TENYyY8lF1I4EgKLcwRvxy820BgWpd)

<h4>Introduction:- Angular</h4>
Angular is framework supported by Google, which lets you build Progressive Web apps, mobile apps for iOS, Android, Windows environment and desktop software for Windows, Mac and Linux machines.<br>
<a href="http://angular.io" target="_blank">angular.io</a><br>

<h4>Introduction:- Ionic Capacitor</h4>
Capacitor is a cross-platform app runtime that makes it easy to build web apps that run natively on iOS, Android, Electron, and the web.<br>
<a href="https://capacitor.ionicframework.com/" target="_blank">capacitor.ionicframework.com/</a><br>

<h4>Single Codebase, Server-less or multiple platforms/database:</h4>
My goal for this Angular development environment setup is to build, real world applications using a single code base for desktop and mobile apps.<br>
I will try to setup my development environment in such way, that a single code base can serve desktop, mobile apps for different platform. Like iOS, Android, Windows and Linux desktop and mobile apps.<br>

Also, my goal is use same codebase to support different hosting and databases with minimal changes.<br>

<h4>Let’s get started :</h4>
-------------------------------------------

I have been using Apache Cordova framework to build cross platform mobile apps. The reasons I want to try out and looking forward to Ionic Capacitor framework are
<ul>
<li>Capacitor fits into existing "package.json" Angular, React or any project. No separate setup is required.</li>
<li>Capacitor Pro version will allow iOS development on Windows or any other machine.</li>
<li>Built-in Electron app functionality.</li>
<li>Built-in PWA (Progressive Web App) functionality.</li>
<li>backwards-compatible support for many existing Cordova plugins.</li>
</ul>

<h5>Capacitor Required Dependencies</h5>
$ node -v // make sure node is 8.6.0+<br>
$ npm -v // make sure node is 5.6.0+<br>

<h5>iOS - Capacitor Required Dependencies</h5>
Mac with Xcode 9 or above.<br> Soon, you'll be able to use Ionic Pro to build for iOS even if you're on Windows.<br>
install CocoaPods (sudo gem install cocoapods)<br>
 install the Xcode Command Line tools (either from Xcode, or running xcode-select --install)<br>

<h5>Android - Capacitor Required Dependencies</h5>
JAVA 8 SDK<br>
ANDROID ADK + ANDROID STUDIO<br>
//Target API Level 21

<h5>PWA - Capacitor Required Dependencies</h5>
JavaScript project with module loading support. For example, using Webpack or Rollup<br>

<h5>Electron - Capacitor Required Dependencies</h5>
JavaScript project with module loading support. For example, using Webpack or Rollup<br>

<h4>Development :</h4>
npm run build // for npm projects<br>
ng build // for Angular 6.0+ projects<br>
ionic build // for Ionic projects<br>

<h4>Capacitor : PWA - Progressive Web App</h4>
<h5>With a Build System</h5> // if you are using Angular or React npm build (like ng build)<br>
** Directly call capacitor in your code<br>
import { Capacitor } from '@capacitor/core';<br>
import { Plugins } from '@capacitor/core';<br><br>
const position = await Plugins.Geolocation.getCurrentPosition();<br>
<h5>Running Natively and on the Web</h5>
import { Capacitor } from '@capacitor/core';<br><br>
const isAvailable = Capacitor.isPluginAvailable('Camera');<br><br>

if (!isAvailable) {<br>
  // Have the user upload a file instead<br>
} else {<br>
  // Otherwise, make the call:<br>
  Camera.getPhoto()<br>
}<br>
<h5>Without a Build System</h5><br>
** update capacitor.config.json<br>
{<br>
  "bundleWebRuntime": true<br>
}<br><br>
npx cap copy web<br>
In index.html, import capacitor.js before your app's JS:<br>
< script src="capacitor.js" >< /script >  // remove extra space in script tag<br>
< script src="your/app.js" >< /script >// remove extra space in script tag<br>
npx cap serve<br>
When you're ready to publish your Progressive Web App and share it with the world, just upload the contents of your web directory (default: public/<br>

<h4>Capacitor : iOS</h4>
npx cap copy ios// Once your web code is built, it needs to be copied to each native project<br>
npx cap open ios<br><br>

<h4>Capacitor : Android</h4>
npx cap copy android// Once your web code is built, it needs to be copied to each native project<br>
npx cap open android<br><br>

<h5>Commands to remember for later use</h5>
npx cap copy
npx cap open<br><br>
npx cap serve // for progressive web apps<br><br>
npx cap update<br>
npm install really-cool-plugin<br>
npx cap update // after plugin install<br>
npx cap sync<br<>>
<br>
<h5>Add this to package.json</h5>
{<br>
  "scripts": {<br>
    "build": "command-to-build (ex: webpack, tsc, babel, etc.)"<br>
  }<br>
}<br>
