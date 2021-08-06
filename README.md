## Vue Ionic + Capacitor Android Base Project
Base project using this tecnologies to easily create and Web/Android app. It also as installed geolocation plugin of Capacitor, to test Android
native functions and permissions.

How it was created:

```
npm install -g @ionic/cli
ionic start myApp tabs --type vue
npm install @capacitor/core @capacitor/cli
npx cap init my.app com.nojeda.myapp --web-dir=dist
npm run build
npm i @capacitor/ios @capacitor/android
npx cap add android
npm install @capacitor/geolocation # Optional
npx cap sync
```

How to install this project:

```
npm install -g @ionic/cli
npm install
npm run build
npx cap add android
npx cap sync
```
