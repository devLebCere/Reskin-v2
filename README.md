# The Reskins Method

A customized Taskbar-based Android project. This source tree adds a white taskbar/black accent default, adjustable taskbar icon size and overall taskbar size controls, and a navigation-bar auto-hide toggle in Appearance settings. Windows 10/Windows 11 visual themes remain a separate future implementation.

Original upstream project and license notices are retained below.

![The Reskins Method](http://i.imgur.com/gttRian.png)

# The Reskins Method

A community-modified build of Taskbar by Braden Farmer. This initial customization updates the app's visible branding; Windows 10/Windows 11 visual theme implementation is a separate next step and is not yet included in this source package.

## Planned reskin themes
- Windows 10-inspired taskbar and Start menu
- Windows 11-inspired centered taskbar and modern Start menu
- A theme selector to switch between the two

This project is based on the original Taskbar source. Preserve the original LICENSE and NOTICE files and review their requirements before redistributing builds.

## Original Taskbar features
* Start menu - shows you all applications installed on the device, configurable as a list or as a grid
* Recent apps tray - shows your most recently used apps and lets you easily switch between them
* Collapsible and hideable - show it when you need it, hide it when you don't
* Many different configuration options - customize Taskbar however you want
* Pin favorite apps or block the ones you don't want to see
* Designed with keyboard and mouse in mind
* 100% free, open source, and no ads

#### Desktop mode (Android 10+, requires external display)
Taskbar supports Android 10's built-in desktop mode functionality. You can connect your compatible Android 10+ device to an external display and run apps in resizable windows, with Taskbar's interface running on your external display and your existing launcher still running on your phone.

Desktop mode requires a USB-to-HDMI adapter (or a lapdock), and a compatible device that supports video output. Additionally, certain settings require granting a special permission via adb.

To get started, open up the Taskbar app and click "Desktop mode". Then, just tick the checkbox and the app will guide you through the setup process. For more information, click the (?) icon in the upper-right hand corner of the screen.

#### Freeform window mode (Android 7.0+, no external display required)
Taskbar lets you launch apps in freeform floating windows on Android 7.0+ devices.  No root access is required, although Android 8.0, 8.1, and 9 devices require an adb shell command to be run during initial setup.

Simply follow these steps to configure your device for launching apps in freeform mode:

1. Check the box for "Freeform window support" inside the Taskbar app
2. Follow the directions that appear in the pop-up to enable the proper settings on your device (one-time setup)
3. Go to your device's recent apps page and clear all recent apps
4. Start Taskbar, then select an app to launch it in a freeform window

For more information and detailed instructions, click "Help & instructions for freeform mode" inside the Taskbar app.

## Changelog
To see some of the major new features in the latest Taskbar release, visit the [changelog](https://github.com/farmerbb/Taskbar/blob/master/CHANGELOG.md).

## Download
Taskbar can be downloaded as a standalone Android app from:

[<img src="https://play.google.com/intl/en_us/badges/images/generic/en_badge_web_generic.png"
      alt="Google Play"
      height="80"
      align="middle">](https://play.google.com/store/apps/details?id=com.farmerbb.taskbar)
[<img src="https://fdroid.gitlab.io/artwork/badge/get-it-on.png"
      alt="F-Droid"
      height="80"
      align="middle">](https://f-droid.org/packages/com.farmerbb.taskbar/)

Taskbar is also included as part of the following Android distributions for PCs:

* Android-x86 (7.1-rc2 and later) (http://www.android-x86.org)
* Bliss OS (x86 builds) (https://blissroms.com)

## How to Build
Prerequisites:
* Windows / MacOS / Linux
* JDK 8
* Android SDK
* Internet connection (to download dependencies)

Once all the prerequisites are met, make sure that the `ANDROID_HOME` environment variable is set to your Android SDK directory, then run `./gradlew assembleFreeDebug` at the base directory of the project to start the build. After the build completes, navigate to `app/build/outputs/apk/free/debug` where you will end up with an APK file ready to install on your Android device.

### Running tests

Taskbar uses [Robolectric](https://github.com/robolectric/robolectric) as its unit testing framework.  The entire test suite can be run with `./gradlew testFreeDebug`, or you can generate a Jacoco coverage report using `./gradlew jacocoTestFreeDebugUnitTestReport` which will be output to the `app/build/jacoco/jacocoHtml` directory.  If you contribute code improvements such as bug fixes, we recommend writing tests alongside it using Robolectric.

## For Third-Party App Developers

#### Android 10 Desktop Mode support via libtaskbar
Taskbar can now be included as a library inside any third-party launcher, to quickly and easily add Android 10 Desktop Mode support into your existing launcher with no additional setup.

For more information on including Taskbar inside your application, see the [libtaskbar documentation](https://github.com/farmerbb/libtaskbar/blob/master/README.md).

#### Icon Pack Support
Taskbar includes support for ADW-style icon packs.  If you are an icon pack developer and would like to include support for applying the icon pack from within your app, simply use the following code:

    Intent intent = new Intent("com.farmerbb.taskbar.APPLY_ICON_PACK");
    intent.putExtra("android.intent.extra.PACKAGE_NAME", "com.iconpack.name");
    startActivity(intent);

## Contributors

Pull requests are welcome!  See the [contributor guidelines](https://github.com/farmerbb/Taskbar/blob/master/CONTRIBUTING.md) for more details.

* Mark Morilla (app logo)
* naofum (Japanese translation)
* HardSer (Russian translation)
* OfficialMITX (German translation)
* Whale Majida (Chinese translation)
* Mesut Han (Turkish translation)
* Zbigniew Zienko (Polish translation)
* utzcoz (Additional Chinese translation, code cleanup + unit testing)
* RaspberryPiFan (Additional German translation)
* Diego Sangunietti (Spanish translation)
* Tommy He (Chinese translation for Desktop Mode)
* Aaron Dewes (German translation updates)
* Ingo Brückl (German translation updates)

#### Special Thanks
* Mishaal Rahman (xda-developers)
* Jon West (Team Bliss)
* Chih-Wei Huang (Android-x86)

## The Reskins Method customizations

This fork adds a default white taskbar background/black accent palette, taskbar icon-size and overall taskbar-size preferences, a navigation-bar auto-hide preference, and a Reskin Store selector with starter profiles (Classic Black & White, Windows 10-inspired, Windows 11-inspired, macOS-inspired, and ChromeOS-inspired). The selector currently applies the base light palette; the named profiles are starter presets and do not yet recreate every platform's exact layout, Start menu, or icon alignment.


## The Reskins Method modifications

This fork adds a built-in Reskin Store with color presets (Classic Black & White, Windows 10-inspired, Windows 11-inspired, macOS-inspired, and ChromeOS-inspired), user-selectable taskbar icon sizing, overall taskbar scaling, and a navigation-bar auto-hide setting in Appearance. The platform-inspired presets currently change the taskbar palette; they do not replace the underlying Taskbar layout with a complete replica of each operating system.

The default palette is white with black accents. Changes to appearance settings restart Taskbar so the selected settings can be applied. Building the Android APK requires the Gradle distribution and Android build dependencies to be available.


## Black-and-white app UI update

The default light UI palette has been adjusted to use a white background, black primary text and controls, and a light status/navigation bar on supported Android versions. Dark-theme resources are retained for the app's explicit dark theme. This source change has not been built into an APK or device-tested in this environment.
