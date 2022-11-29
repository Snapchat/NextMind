# Changelog

Current (latest) version of the NextMind Unity SDK is: 

## 1.5.1

_Release date : 14 February 2022_

#### Changed

- API Reference/Comments: enhance data + fix typos.
- Core: ConnectedDeviceStatus prefab now displays "--" instead of 0 when the battery value has still not be received.
- Core: [BREAKING] refactor BLEEvent.BLEEventType to BLEEvent.Type.
- Demos: fix bug where selecting a new channel in NeuroTV unmute without hiding the icon. It now keeps the audio muted.
- Demos: fix bug where top-right menu was inaccessible at Platformer's start.
- Examples: videos switched to WebM format.
- Examples: bugfix in SDKDiscovery's last step where 2 objects could be cut at the same time.
- EventNotifier: better management of messages (stack messages).
- NeuroTag Gallery: refactor scene's objects names and enhance comments.
- NeuroTag Gallery: hide the triangle feedback when the stimulation is stopped.
- NeuroTags: fix bug where only the first material of a Stimulation Renderer's materials was used for the stimulation.
- NeuroTags: "Fix" button on NeuroTags is only display if ALL the materials of the renderer are not NextMind compatible.
- NeuroTags: update confidence values before invoking trigger/release events. Fixes confidence values being reset to 1 when a neurotag is disabled upon a trigger event.
- NeuroTags: fix bug where SetNeuroTagBehaviour called from Awake has no effect.
- Shaders: fix differences between SRP and Built-in shaders.

#### Added

- Core: display more explicit warnings (console and editor), mainly when there are too much NeuroTags in the scene.
- Core: new ContactGradeEvent and methods GetContactGrade() and GetNormalizedContactGrade().
- Editor: new Welcome panel displayed on SDK importation, asking the user if Unity should add the example scenes to build settings.
- Shaders: add Metallic and Glossiness properties to SRP Lit shaders.
- Calibration: CalibrationGrade enumeration has a new UNDEFINED value.

#### Removed

- Calibration scene : remove unused SelectedDeviceStep.
- Core: [BREAKING] remove OTAEvent class.

<hr style="margin-top: 40px;opacity: 0.1;">

## 1.5.0

_Release date : 30 June 2021_

#### Changed

- Bugfix : battery indicator showing the connected device's battery level correctly
- Bugfix : ContactsVisualization prefab layout corrected
- Better handling of NeuroTag tracking/untracking
- The Overlay Blending property is deprecated and will be removed. In future versions of the SDK, Overlay Blending will automatically be active.

#### Added

- New example scene : NeuroTag Gallery
- Allow to declare multiple Tracking Cameras on NeuroManager
- Scriptable Render Pipeline assets (prefabs, materials, and example scenes) are available. See SRP folders and example folder's README file
- Warning messages displayed on shaders editors when their configuration is not optimal
- New error and warning messages (e.g. NextMindManager is not installed, bad bluetooth connection, ...)

<hr style="margin-top: 40px;opacity: 0.1;">

## 1.4.0

_Release date : 05 May 2021_

#### Changed

- Calibration results are computed much faster
- Various back-end optimizations
- Fix some cases where "Unknown BCI error" was thrown
- Unity 2018 is not supported anymore

#### Added

- New help video at the end of the calibration giving tips on how to get a better score

<hr style="margin-top: 40px;opacity: 0.1;">

## 1.3.2

_Release date : 09 April 2021_

#### Changed

- Bugfix : NeuroTag's "Fix" button failed if the developer moved or renamed the NextMindSDK folder, or get it from UPM
- Bugfix : Simulation mode on Collider2D with perspective Camera
- Bugfix : shadergraphs triplanar projection was using world space normals instead of local space
- Bugfix : shadergraphs "Constant size" property was creating deformation artefacts on stimulation texture
- Use Gradient on ContactsVisualization instead of 2 colors
- Remove "Screen Ratio" property from Nextmind's shaders. This is now computed automatically

#### Added

- Contact Quality is now visible in the profiler, and accessible through script using Device.GetAverageContactQuality()

<hr style="margin-top: 40px;opacity: 0.1;">

## 1.3.1

_Release date : 23 March 2021_

#### Changed
- Bugfix : NeuroTags visibility calculation on World Space Canvases
- Bugfix : OnReleased event is now triggered when destroying/disabling a NeuroTag 

<hr style="margin-top: 40px;opacity: 0.1;">

## 1.3.0
_Release date : 12 March 2021_

#### Added

- Introducing the Changelog !
- First release of UPM packages
- UWP platforms support (x86 & ARM64) : allowing Hololens 1 & 2 software compatibility
#### Changed

- Shaders property OverlayColor has been removed for simplicity sake
- Enhance bluetooth connection stability : adaptive data rate and collisions mitigation.
- Improved NextMindManager/Installer GUI
- Bugfix : overlay blending was not applied properly
- Bugfix : NeuroManager events callbacks (OnDeviceAvailable/Unavailable & OnDeviceConnected/Disconnected) were not called by the right events
- Bugfix : Simulated feedback was not reset when a target is reassigned