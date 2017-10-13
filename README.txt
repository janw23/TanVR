Demo video: https://www.youtube.com/watch?v=L9VjQKvirxs

Setup instruction (Unity version 2017.2.0b9):
1. Imports:
- Download and import Google ARCore SDK for Unity https://developers.google.com/ar/develop/unity/getting-started
- Import TanVR package to your project

2. ARCore modifications:
In order to disable device's camera overlay ARCore's script has to be modified (you can change original one or just create a copy and then swap it where needed).
I was not able to publish already modified version because license doesn't allow to do that so here are the changes you have to make:
- Find script "SessionComponent", it should be in GoogleARCore/SDK/Scripts.
- Find declaration of function "_ConnectToService" (somewhere near 225th line).
- Remove or comment call to function "_SetupVideoOverlay" from previously mentioned function.

3. Scene preparation:
- Move "ARCore Device" prefab from TanVR to your scene and make sure there are no missing components or variables.
I would recommend setting transform.position.y of this GameObject to your real height so the floor level would be the same as in reality.

- The last thing you have to do is to enable "Tango Supported" and "Virtual Reality Supported" in XR in player settings.

Important:
- This is not any kind of professional project, it is only my own experiment.
- Your phone has to be compatible with Tango and "Tango Services" has to be installed.
- I do not provide scene assets from my demo video, you have to put objects yourself.
- When running your project in editor tango_client_api2 error may occur but this should work just fine on your phone.
- I've tested it only on Unity 2017.2.0b9 and I can't guarantee that it works on other versions (probably doesn't work on older).

By Jan Wawszczak