## Issue with api levels + deps
* Issue appears after updating deps in build.gradle to newer versions

### Beofre (build.gradle)

```
  implementation 'org.greenrobot:eventbus:3.0.0'
  implementation 'com.github.wrdlbrnft:modular-adapter:0.2.0.6'
  implementation 'com.github.wrdlbrnft:sorted-list-adapter:0.2.0.19'
  implementation 'com.simplecityapps:recyclerview-fastscroll:1.0.16'
  implementation 'de.psdev.licensesdialog:licensesdialog:1.8.3'
  implementation 'com.github.GrenderG:Color-O-Matic:1.1.5'
  implementation 'androidx.annotation:annotation:1.2.0'
  implementation 'androidx.cardview:cardview:1.0.0'
  implementation 'androidx.appcompat:appcompat:1.3.0'
  implementation 'androidx.appcompat:appcompat-resources:1.3.0'
  implementation 'com.google.android.material:material:1.4.0-rc01'
  implementation 'com.afollestad.material-dialogs:lifecycle:3.3.0'

  implementation 'androidx.compose.ui:ui:1.0.0-beta08'
  // Tooling support (Previews, etc.)
  implementation 'androidx.compose.ui:ui-tooling:1.0.0-beta08'
  // Foundation (Border, Background, Box, Image, Scroll, shapes, animations, etc.)
  implementation 'androidx.compose.foundation:foundation:1.0.0-beta08'
  // Material design icons
  implementation 'androidx.compose.material:material-icons-core:1.0.0-beta08'
  implementation 'androidx.compose.material:material-icons-extended:1.0.0-beta08'
  implementation 'androidx.compose.material:material:1.0.0-beta08'
  // Integration with activities
  implementation 'androidx.activity:activity-compose:1.3.0-beta01'
  // Integration with ViewModels
  implementation 'androidx.lifecycle:lifecycle-viewmodel-compose:1.0.0-alpha06'
  // Integration with observables
  implementation 'androidx.compose.runtime:runtime-livedata:1.0.0-beta08'
  implementation 'androidx.compose.runtime:runtime-rxjava2:1.0.0-beta08'
```

### After (build.gradle)

```
  implementation 'org.greenrobot:eventbus:3.0.0'
  implementation 'com.github.wrdlbrnft:modular-adapter:0.2.0.6'
  implementation 'com.github.wrdlbrnft:sorted-list-adapter:0.2.0.19'
  implementation 'com.simplecityapps:recyclerview-fastscroll:1.0.16'
  implementation 'de.psdev.licensesdialog:licensesdialog:1.8.3'
  implementation 'com.github.GrenderG:Color-O-Matic:1.1.5'
  implementation 'androidx.annotation:annotation:1.2.0'
  implementation 'androidx.cardview:cardview:1.0.0'
  implementation 'androidx.appcompat:appcompat:1.3.1'
  implementation 'androidx.appcompat:appcompat-resources:1.3.1'
  implementation 'com.google.android.material:material:1.5.0-alpha01'
  implementation 'com.afollestad.material-dialogs:lifecycle:3.3.0'

  implementation 'androidx.compose.ui:ui:1.0.0-rc02'
  // Tooling support (Previews, etc.)
  implementation 'androidx.compose.ui:ui-tooling:1.0.0-rc02'
  // Foundation (Border, Background, Box, Image, Scroll, shapes, animations, etc.)
  implementation 'androidx.compose.foundation:foundation:1.0.0-rc02'
  // Material design icons
  implementation 'androidx.compose.material:material-icons-core:1.0.0-rc02'
  implementation 'androidx.compose.material:material-icons-extended:1.0.0-rc02'
  implementation 'androidx.compose.material:material:1.0.0-rc02'
  // Integration with activities
  implementation 'androidx.activity:activity-compose:1.3.0-rc02'
  // Integration with ViewModels
  implementation 'androidx.lifecycle:lifecycle-viewmodel-compose:1.0.0-alpha07'
  // Integration with observables
  implementation 'androidx.compose.runtime:runtime-livedata:1.0.0-rc02'
  implementation 'androidx.compose.runtime:runtime-rxjava2:1.0.0-rc02'
```

### Log (from after)

* Build output

```
The minCompileSdk (30) specified in a
dependency's AAR metadata (META-INF/com/android/build/gradle/aar-metadata.properties)
is greater than this module's compileSdkVersion (android-28).
Dependency: androidx.compose.ui:ui-tooling:1.0.0-rc02.
AAR metadata file: /home/hilledkinged/.gradle/caches/transforms-3/cfbffc4bb899072b9ff215ca6821e076/transformed/jetified-ui-tooling-1.0.0-rc02/META-INF/com/android/build/gradle/aar-metadata.properties.
```

* Event log

```
7/28/21
12:13 PM	* daemon not running; starting now at tcp:5037

12:13 PM	* daemon started successfully

12:14 PM	Gradle sync started

12:15 PM	Gradle sync finished in 1 m 1 s 312 ms

12:15 PM	Plugin Update Recommended: Android Gradle Plugin is ready to update.

12:16 PM	Executing tasks: [:xwayland:assembleDebug, :app:assembleDebug] in project /run/media/hilledkinged/projects/pwn-stuff/PWN-Term-gen2

12:16 PM	Gradle build failed in 22 s 974 ms
```
