# warpAR (WIP)

warpAR is an augmented reality app for iOS that lets you distort the textures of the real world by tapping and dragging. Tap and drag to reshape buildings or turn murals into swirls of color using a set of liquify tools. The app is [available for free on the app store][app].

This repo provides documentation on using warpAR. If you run into any issues or have any feature requests, you can also [file an issue][issues] here.

## Using the app

### Placing the AR plane

To get started with warpAR, first you need to select a real world surface that you'd want to distort. You can place the effect on any flat horizontal or vertical surfaces. The app will walk you through the placement process.

> 🎵 **Note**: Pinch to scale the placed plane up and down. This also works after you have placed the plane.

If you are having trouble placing the effect:

- Try moving the device about a little. On devices without a LiDAR sensor, this helps with surface detection.
- Make sure there is enough light for the cameras. Surface detection struggles in low light.
- Use a surface that has some visual details. Surface detection struggles when pointed at solid color surfaces, such as white walls.

### Tools

The push tool is selected by default and lets you shift around parts of the world's texture by tapping and dragging.

Tap on the tool icon in the center of the bottom bar to adjust the push tool or switch to another tool. The complete set of tools:

- `push` — Move around parts of the world's textures by tapping and dragging.
- `restore` — Move the texture back to its original, undistorted state.
- `Bloat` — Expand the texture outwards from the center.
- `Pucker` — Collapse the texture inwards from the center.
- `Swirl Left` — Swirl the texture to the left (counterclockwise) around the center.
- `Swirl Right` — Swirl the texture to the right (clockwise) around the center.

Each tool has two settings:

- `radius` — How large of an area will be distorted around where you tap. This is expressed in meters. 
- `strength` — How strong the effect will be. With push for example, lower strength means that parts of the image will shift around less when you tap and drag.

To quickly clear the distorting, tap in the `...` in the bottom bar and select `Reset Distortion`

### Sharing

Tap the circular camera button to capture a screenshot of the current effect. This screenshot hides all UI elements so that you only see the effect.

Tap and hold the camera button to start recording a video. This starts a countdown, with recording starting after three seconds. Tap the camera button again to stop recording. While recording, you can interact with the app and continue using the tools. Videos also record the microphone input.

After taking a video or screenshot, you can download it to your photos or share it using the standard iOS share sheet.


## Advanced options

Note that both of these advanced options require a device with a LiDAR sensor, such as the iPhone 12 Pro.

### Foreground occlusion

Foreground occlusion uses depth data from the LiDAR sensor to avoid distorting objects that appear in front of the distorted canvas. This foreground object could be a person, your hand, or a wall. The result makes it look like the effect is better integrated into the world instead of merely being an effect on your screen.

To enable foreground occlusion, tap the lightbulb icon and toggle "Foreground Occlusion". Keep in mind that the effect is not perfect. If you don't need it, I suggest turning the feature off.

For best results with foreground occlusion:

- Make sure the distortion plane is exactly placed on the real world surface. You may notice significant issues if the plane is placed a few cm above or below the real surface. 

- Only enable foreground occlusion if the surface is flat. If the surface is angled or pitted, foreground occlusion may cause weird artifacts.

- Keep in mind that objects only a few cm from the surface will be considered part of the surface. Foreground occlusion works best when there is at least a 25cm difference in depth between the foreground object and the surface (although the margin it uses internally is closer to 10cm). 

- Foreground objects can only be around 4 meter from the phone. This is a limitation of the LiDAR sensor.

## Feedback

Love warpAR? Be sure to tell your friends about it and share any cool content you create using the app. If you are feeling especially generous, please also write an App Store review. This really helps other people find the app.

Run into a bug or want to request a new feature? Just [file an issue][issues]!

[app]: https://apps.apple.com/us/app/warpar/id1557413470
[issues]: https://github.com/mattbierner/warpar-support/issues
