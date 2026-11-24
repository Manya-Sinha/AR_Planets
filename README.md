# Planets AR

An Android augmented reality guide to the solar system, built with Unity 6, AR Foundation and ARCore. Pick a planet from the home screen and see a textured, rotating 3D model of it placed in front of you through your phone's camera.

**[Download the latest release (APK and project files)](../../releases/latest)**

## Features

- Home screen with a button for each of the eight planets
- Textured 3D planets (Saturn includes its rings)
- Live AR camera view using ARCore
- Continuous planet rotation
- Back button on every planet screen
- Planet automatically placed in front of the camera when a scene opens

## Requirements

**To run the app**
- Android 7.0 (API 24) or higher
- A phone that supports ARCore ([supported devices](https://developers.google.com/ar/devices))
- Google Play Services for AR installed (the Play Store offers it if missing)

**To open the project**
- Unity **6000.0.85f2** (Unity 6) with the **Android Build Support** module (OpenJDK and Android SDK & NDK Tools)
- Visual Studio or another C# editor

## Download

Go to the **Releases** page and download the release zip. It contains:

| Item | Description |
|---|---|
| `Planets AR.apk` | Ready-to-install Android app |
| `Assets/` | Scenes, scripts, textures, materials and models |
| `Packages/` | Package manifest (AR Foundation, ARCore XR Plugin, etc.) |
| `ProjectSettings/` | Unity project settings |

## Install the APK

1. Copy `Planets AR.apk` to your phone.
2. Open it and allow installs from this source if Android asks.
3. Launch **Planets AR** and allow camera access.
4. Point your phone at a well-lit area, tap a planet, and wait a moment while AR starts tracking.

## Open the project in Unity

1. Extract the release zip into a new folder (for example `PlanetsAR`).
2. In Unity Hub, click **Add > Add project from disk** and select that folder.
3. Open it with Unity **6000.0.85f2**. The first import takes a few minutes, and Unity rebuilds the `Library` folder on its own.
4. Open the `HomeScreen` scene from `Assets/Scenes`.

## Build the APK yourself

1. Open **File > Build Profiles**, select **Android** and click **Switch Platform**.
2. Check that **Scene List** contains every scene, with `HomeScreen` first.
3. Under **Edit > Project Settings > XR Plug-in Management > Android**, make sure **ARCore** is ticked.
4. Under **Project Settings > Player > Other Settings**, confirm: Minimum API Level 24 or higher, Scripting Backend IL2CPP, Target Architecture ARM64.
5. Connect your phone with USB debugging on, then click **Build And Run**, or click **Build** and install the APK manually.

## How it works

Every planet scene contains an **AR Session** and an **XR Origin (Mobile AR)**, which provide the camera feed and tracking. The planet is placed a short distance in front of the camera once tracking begins, then stays fixed in the room as you move.

### Scenes

`HomeScreen`, `Mercury`, `Venus`, `Earth`, `Mars`, `Jupiter`, `Saturn`, `Uranus`, `Neptune`

### Scripts

| Script | Purpose |
|---|---|
| `RotationControllerPlanet` | Rotates the planet each frame using a rotation vector set in the Inspector |
| `SceneSwitcher` | Loads a scene by name; used by the planet buttons and Back buttons |
| `PlanetPlacer` | Hides the planet until AR is tracking, then places it in front of the camera |

## Built with

- Unity 6 (6000.0.85f2), Built-In Render Pipeline
- AR Foundation 6.x
- Google ARCore XR Plugin
- C#

## Credits

- Planet textures, UI images and the Saturn model by Body Clone
- Based on a Unity AR tutorial project, adapted for Unity 6.

## Author

Manya Sinha

