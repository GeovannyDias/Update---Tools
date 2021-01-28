# Update - Tools
Update Ionic / Angular / TypeScript / more...


# IONIC 4 to 5

**CLI**
```
Ionic CLI update available: 5.2.8 → 5.4.14 // x.x.x → x.x.x
    Run npm i -g ionic to update
            
npm i -g ionic

ionic info

cordova plugin list

```
**Upgrade the existing Ionic 4 app to Ionic 5 and Add New Feature**
* **https://www.djamware.com/post/5e409668d598ef51b8a6aaa7/upgrade-the-existing-ionic-4-app-to-ionic-5-and-add-new-feature**

```
Step #1. Clone the existing Ionic 4 app.
git clone

Step #2. Go to the newly cloned Ionic app.
cd ionic-project

Step #3. Install all require NPM and run every required NPM command.
npm i
npm fund
npm audit fix
npm audit fix --force

(Otptional):
Step #4. Run this Ionic app to check everything is working.
ionic serve -l

Step #5. Add the platforms and run to the device after stop the running Ionic 4 lab by press CTRL + C.
ionic cordova platform add ios
ionic cordova platform add android

Step #6. Run iOS and Android to device or emulator.
ionic cordova run ios
ionic cordova run android


Actualizar @angular-devkit/build-angular

npm audit fix
npm audit fix --force

```
**Upgrade to Ionic 5**

```
Step #1. Update the Ionic CLI globally.
sudo npm i -g ionic

Step #2. Update the @ionic/angular for this project.
npm i @ionic/angular

Step #3. If required run this NPM command.
npm fund

Step #4. Upgrade the Ionic 4 to Ionic 5.
npm install @ionic/angular@next

Step #5. Open this Ionic app using your IDE or text editor. To use VSCode type this.
code .

```

**Check the Upgraded Ionic App**
* **We need to check the upgraded Ionic app to make sure everything is working as expected. Follow these steps to checks:**

```
Step #1. Open the package.json with your IDE or Text Editor and see if there is the latest version of @ionic/angular.
"dependencies": {
    ...
    "@ionic-native/core": "^5.0.0",
    "@ionic-native/splash-screen": "^5.0.0",
    "@ionic-native/status-bar": "^5.0.0",
    "@ionic/angular": "^5.0.0-rc.3",
    ...
  },

Step #2. Run again the newly upgraded Ionic App.
ionic serve -l
Step #3. It seems everything is working, except the list-icon disappears. That because the new Ionicons version deleted the list-box. So, we need to change that icon to this icon that renamed in the new Ionicons version by open and edit "src/app/tab1/tab1.page.html" then replace the list-box icon with this.

<ion-icon slot="icon-only" name="newspaper"></ion-icon>

Step #4. Centering the header content using the new Ionic 5 CSS utilities. Add this CSS class to every tab page header and <ion-card>.
<ion-header class="ion-text-center">
...
<ion-card [routerLink]="['/tabs/tab2/', p.id]" class="ion-text-center">

Step #5. Give a padding to the <ion-card> content.
<img src="{{p.photo}}" class="ion-padding" />
<ion-card-header class="ion-padding">

Step #6. Change the text in <ion-list-header> to wrapped text by <ion-label> in order to get the proper styling of the new design.
<ion-list-header>
    <ion-label>Premier League Legend</ion-label>
</ion-list-header> 

```

**Add a New Core Ionic 5 Feature**

* **https://www.djamware.com/post/5e409668d598ef51b8a6aaa7/upgrade-the-existing-ionic-4-app-to-ionic-5-and-add-new-feature**

# ERROR IONIC / ANGULAR UPDATE

**An unhandled exception occurred: Job name “..getProjectMetadata” does not exist**
* **https://stackoverflow.com/questions/59447679/an-unhandled-exception-occurred-job-name-getprojectmetadata-does-not-exist**

```
For IONIC 5 the following downgrades worked for me.

npm i @angular-devkit/build-angular@0.803.25

npm i @angular-devkit/build-angular@0.803.24

Other versions has a high vulnerability warning and risks

```

**Ionic 4: Ionic cordova resources fails with node error**
* **https://forum.ionicframework.com/t/ionic-4-ionic-cordova-resources-fails-with-node-error/176944**

```
ionic cordova resources

> cordova-res.cmd
[cordova-res]
[cordova-res] Something went wrong installing the "sharp" module
[cordova-res]
[cordova-res] Module did not self-register: '\\?\C:\Users\Geo\AppData\Roaming\npm\node_modules\cordova-res\node_modules\sharp\build\Release\sharp.node'.
[cordova-res]
[cordova-res] - Remove the "node_modules/sharp" directory, run "npm install" and look for errors
[cordova-res] - Consult the installation documentation at https://sharp.pixelplumbing.com/en/stable/install/
[cordova-res] - Search for this error at https://github.com/lovell/sharp/issues
[cordova-res]
[ERROR] An error occurred while running subprocess cordova-res.

Solution:

npm remove cordova-res
npm install cordova-res

```

**Other Error Ionic
**Ionic 4: Execution failed for task ‘:app:processDebugResources’**

* **https://forum.ionicframework.com/t/ionic-4-execution-failed-for-task-processdebugresources/162937**
* **https://stackoverflow.com/questions/49162538/running-cordova-build-android-unable-to-find-attribute-androidfontvariation/57012475#57012475**

```

cordova plugin add cordova-android-support-gradle-release --fetch

I found the solution on Ionic Forum, which was the only solution that worked for me:

Run:

ionic cordova platform rm android

Run:

ionic cordova platform add android@8.0.0

Run:

ionic cordova plugin add cordova-plugin-androidx

Run:

ionic cordova plugin add cordova-plugin-androidx-adapter

Make sure your gradle.properties has:

cdvMinSdkVersion=19

Make sure your build.gradle has:

project.ext { defaultBuildToolsVersion="28.0.3" //String 

defaultMinSdkVersion=19 //Integer - Minimum requirement is Android 4.4 

defaultTargetSdkVersion=28 //Integer - We ALWAYS target the latest by default 

defaultCompileSdkVersion=28 //Integer - We ALWAYS compile with the latest by default }
Make sure your config.xml has:

<preference name="android-minSdkVersion" value="19" />
from: https://forum.ionicframework.com/t/firebase-app-unable-to-compile-on-android-with-aapt-error/166564/7

which is also handled in the stackoverflow answer: https://stackoverflow.com/a/56656680/839691

```

**An unhandled exception occurred: [BABEL]**

```
An unhandled exception occurred: [BABEL] D:\Developer_Studio\Proyectos\Jemadental\jemadentalweb-movil\JemaDentalM\www\1-es2015.js: Could not find plugin "proposal-numeric-separator". Ensure there is an entry in ./available-plugins.js for it. (While processing: "D:\\Developer_Studio\\Proyectos\\Jemadental\\jemadentalweb-movil\\JemaDentalM\\node_modules\\@babel\\preset-env\\lib\\index.js")
See "C:\Users\Geo\AppData\Local\Temp\ng-GQfN8t\angular-errors.log" for further details.
[ERROR] An error occurred while running subprocess ng.



Intentar:
npm i @babel/compat-data@7.8.0

Intentar:
npm i @angular-devkit/build-angular@0.803.23

Intentar:
D8: Program type already present: android.support.v4.os.ResultReceiver$MyResultReceiver

ionic cordova plugin add cordova-plugin-androidx
ionic cordova plugin add cordova-plugin-androidx-adapter

https://stackoverflow.com/questions/56688570/program-type-already-present-android-support-v4-os-resultreceivermyresultrecei

// Consultar su funcion para reparar problemas:

ionic repair
[INFO] ionic repair will do the following:

       - Remove node_modules/ and package-lock.json
       - Run npm i to restore dependencies
       - Remove platforms/ and plugins/
       - Run cordova prepare to restore platforms and plugins


```

**Execution failed for task ':app:mergeReleaseResources'.**
* **https://forum.ionicframework.com/t/solved-execution-failed-for-task-mergereleaseresources-when-doing-release-prod-build/168994**
* **https://stackoverflow.com/questions/52712063/build-failing-during-merge-resources-with-android-gradle-plugin-3-3-0/54615423#54615423**

```
> java.util.concurrent.ExecutionException: com.android.builder.internal.aapt.v2.Aapt2InternalException: AAPT2 aapt2-3.3.0-5013011-windows Daemon #0: Unexpected error during compile 'D:\Developer_Studio\Proyectos\Restaurante\tesis-3-app-restaurante\restaurante-movil\platforms\android\app\src\main\res\drawable-land-xxxhdpi\screen.png', attempting to stop daemon.
  This should not happen under normal circumstances, please file an issue if it does.
```

```
Este error da por el peso del icono o spash screen de la app, sobre pasa las 2MB

Solve:

Bajar el peso de la imagen PNG menor a 2 MB

```

# ERROR IONIC 5
```
Error 288 FCM //  Desinstalar FCM y ver versione

npm i @angular-devkit/build-angular@0.1000.0

Intalar Firebase:
"@angular/fire": "^5.4.2",
"firebase": "^6.6.2",

Siempre eliminar carpeta node_module y ejecutar npm i

Otra solución:

npm i @angular-devkit/build-angular@0.803.23

Eliminara la plataforma
ionic cordova platform rm android

Instalar:
ionic cordova plugin add cordova-plugin-androidx-adapter
ionic cordova plugin add cordova-plugin-androidx

Eliminara la plataforma
ionic cordova platform add android

ionic cordova build android 


ERROR FCM:

events.js:288 throw er; // Unhandled 'error' event

La nueva versión "^7.6.0" de FCM da conflictos con ionic 5, la solucion es bajar la version de FCM "^6.4.3"
ionic cordova plugin add cordova-plugin-fcm-with-dependecy-updated@6

UNINSTALL FCM:
npm uninstall @ionic-native/fcm
ionic cordova plugin remove cordova-plugin-fcm-with-dependecy-updated

```

# GRADLE - PROBLEMA DE VERSION - DESCONTINUADO

* **https://medium.com/@chenlitchian/you-will-need-to-install-cordova-android-support-gradle-release-if-failed-to-build-due-to-version-e076c9a4ddf8**

```
You will need to install cordova-android-support-gradle-release if failed to build due to version issue. See here.

cordova plugin cordova-android-support-gradle-release

cordova-android-support-gradle-release is a plugin to align various versions of the Android Support libraries specified by other plugins to a specific version.

```


# TYPESCRIPT

```
tsc -v // --version
npm install -g typescript

```
# Angular

**Actualizar Angular CLI para Angular**

* **https://medium.com/@janpierrsanchez/actualizar-angular-cli-para-angular-2aaf8928ce70**
```

npm install -g @angular/cli@latest

Update Global:

npm uninstall -g @angular/cli
npm cache verify
npm cache clean  => (--force)

npm install -g @angular/cli
npm cache verify
npm cache clean  => (--force) => (for older npm versions) After updating both the global and local package, clear the cache to avoid errors.

Other:
npm install -g @angular/cli@^10

Upate Project:

ng update @angular/cli @angular/core
→ OR
ng update @angular/cli@^10 @angular/core@^10

```
**Angular CLI**
* **https://www.npmjs.com/package/@angular/cli**

```
Generating Components, Directives, Pipes and Services
You can use the ng generate (or just ng g) command to generate Angular components:

ng generate component my-new-component
ng g component my-new-component # using the alias

# components support relative path generation
# if in the directory src/app/feature/ and you run
ng g component new-cmp
# your component will be generated in src/app/feature/new-cmp
# but if you were to run
ng g component ./newer-cmp
# your component will be generated in src/app/newer-cmp
# if in the directory src/app you can also run
ng g component feature/new-cmp
# and your component will be generated in src/app/feature/new-cmp

```
**Errores Angular Update**

```
PS D:\Geo\01_Express\web-app\app-web-cainar> ng serve --open

ng : File C:\Users\KUBXY\AppData\Roaming\npm\ng.ps1 cannot be loaded because running scripts is disabled on this system. For more information, see 
about_Execution_Policies at https:/go.microsoft.com/fwlink/?LinkID=135170.
At line:1 char:1
+ ng serve
+ ~~
    + CategoryInfo          : SecurityError: (:) [], PSSecurityException  
    + FullyQualifiedErrorId : UnauthorizedAccess
    

ng serve --open
Error de Visual Studio Code // Correr servidor en otra terminal.

Solution:

I opened VS Code as Administrator and ran this command in the terminal:

Set-ExecutionPolicy Unrestricted

It allowed me to run the scripts without an errors.

```

# ¿Cómo convertir una app de IONIC en una PWA?
* **https://platzi.com/blog/app-ionic-en-pwa/**
* **https://desarrolloweb.com/articulos/primer-progressive-web-app-ionic.html**

```
Verificar que esta instalado en service-worker (En aplications del navegador)

copiar codigo de documentacion en el index.html antes de finalizar el la etiqueta body


ionic build // crea nuevamente la carpeta www/
npm install http-serve // correr modo de produccion app ionic
cd www/
http-serve

```

# Remote Devices
```
Url para comprobar dispositivos:

chrome://inspect/#devices
```

# NPM
```
npm install -g npm to update!
```

