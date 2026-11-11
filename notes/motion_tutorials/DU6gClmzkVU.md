# DU6gClmzkVU
(source: transcript)

**Recipe for the After Effects SaaS Tutorial**

**Background Animation**

1. Create a new solid layer and change its color to white.
2. Duplicate the solid layer and place it on the other side.
3. Use the ellipse tool to create a circle shape layer.
4. Center the anchor point and place the shape layer on the top right corner.
5. Change the color of the shape layer according to the reference.
6. Scale the shape layer if desired.
7. Add a fast box blur effect to the shape layer.
8. Duplicate the shape layer and place it on the other side.

**Text Animation**

1. Create a new text layer and add the text.
2. Center the anchor point and center align the text.
3. Enable title and safe action.
4. Scale the text layer.
5. Use the SF Pro Display font and regular style.
6. Add an opacity animator to the text layer.
7. Add a position animator to the text layer.
8. Add a blur animator to the text layer.
9. Reduce the opacity to zero and increase the blur level to around 10-20.
10. Change the Y position to around 100.
11. Create offset keyframes for the animators.
12. Change the ease high to minus 50 and ease low to 100.

**Drop Shadow Effect**

1. Duplicate the text layer.
2. Open the properties of the top text layer.
3. Select the animator one and duplicate it.
4. Open the properties of the duplicated animator.
5. Offset the keyframes by three frames.

**Fill Effect**

1. Duplicate the text layer.
2. Change the color of the duplicated text layer to whatever you like.
3. Set the mode type to subtract.

**Red Glow Effect**

1. Create a new shape layer.
2. Make the shape like a circle.
3. Center the anchor point.
4. Add some position keyframes to the shape layer.
5. Move the position to the left side at the start.
6. Move the position to the right side at the end.
7. Select both the shape layer and the text layer.
8. Press F9 to make a smooth graph.
9. Change the color of the shape layer to red.
10. Track mat the shape layer with the text layer.

**Camera and Null Moves**

1. Create a new null layer.
2. Move the null layer to the desired position.
3. Create a new camera layer.
4. Move the camera layer to the desired position.
5. Parent the camera layer to the null layer.

**Motion Blur**

1. Enable motion blur in the project settings.
2. Set the motion blur to the desired amount.

**Glow**

1. Create a new shape layer.
2. Make the shape like a circle.
3. Center the anchor point.
4. Add some position keyframes to the shape layer.
5. Move the position to the left side at the start.
6. Move the position to the right side at the end.
7. Select both the shape layer and the text layer.
8. Press F9 to make a smooth graph.
9. Change the color of the shape layer to red.
10. Track mat the shape layer with the text layer.

**Transitions**

1. Use the dissolve transition to transition between scenes.

**UI Mockup Handling**

1. Use the pre-compose feature to handle complex UI mockups.
2. Use the track mat feature to track the UI elements.

**Typography Sizes/Fonts**

1. Use the SF Pro Display font and regular style.
2. Set the font size to the desired amount.

**Background Animation**

1. Use the ellipse tool to create a circle shape layer.
2. Center the anchor point and place the shape layer on the top right corner.
3. Change the color of the shape layer according to the reference.
4. Scale the shape layer if desired.
5. Add a fast box blur effect to the shape layer.
6. Duplicate the shape layer and place it on the other side.

**Sound**

1. Add a sound effect to the project.
2. Use the audio levels to adjust the volume.

**Reproducing in Remotion**

Here is the code-level recipe for the Remotion tutorial:

```javascript
import { interpolate, spring } from 'remotion';

// Background Animation
const background = spring(0, {
  fps: 60,
  mass: 1,
  tension: 300,
  friction: 40,
});

// Text Animation
const text = spring(0, {
  fps: 60,
  mass: 1,
  tension: 300,
  friction: 40,
});

// Drop Shadow Effect
const dropShadow = spring(0, {
  fps: 60,
  mass: 1,
  tension: 300,
  friction: 40,
});

// Fill Effect
const fill = spring(0, {
  fps: 60,
  mass: 1,
  tension: 300,
  friction: 40,
});

// Red Glow Effect
const glow = spring(0, {
  fps: 60,
  mass: 1,
  tension: 300,
  friction: 40,
});

// Camera and Null Moves
const camera = spring(0, {
  fps: 60,
  mass: 1,
  tension:

**Recipe for After Effects SaaS Tutorial**

1. **Text Layer**
	* Enable the text layer.
	* Set the text to: "Are your financial books messy?"
	* Add a Fast Box Blur effect to remove sharp edges.
	* Increase the radius of the blur.
2. **Icon Layer**
	* Import icons into the scene.
	* Adjust the positioning and scale of the icons.
	* Play with the rotation of the icons.
3. **Keyframe Animation**
	* Add keyframes for rotation and scale.
	* Set the rotation keyframes to bounce with an amplitude of 25.
	* Set the scale keyframes to bounce.
4. **Duplicate Icon Layer**
	* Duplicate the icon layer using Control D.
	* Adjust the scale and rotation of the duplicated layer.
5. **Position Keyframes**
	* Add keyframes for position on the main text layer.
	* Set the position keyframes to start at 100 and end at 0.
6. **Trim Layers**
	* Trim the layers at the current point using Control Shift D and delete.
7. **Zoom Transition**
	* Create a new null object.
	* Parent the main layer with the null object.
	* Add an empty keyframe for scale on the null object.
	* Increase the scale of the null object over time.
8. **Second Scene**
	* Create a new text layer.
	* Add the transition of zoom in.
	* Parent the top text layer with the bottom text layer.
	* Center the anchor point and adjust the scale.
9. **Keyframe Animation**
	* Adjust the keyframes of both layers.
	* Add a marker and move the keyframes closer.
10. **Transition**
	* Create a new null object.
	* Parent the bottom text layer with the null object.
	* Add an empty keyframe for scale on the null object.
	* Lower the scale of the null object over time.

**Reproducing in Remotion**

To reproduce this animation in Remotion, you can use the following code:

```jsx
import { spring } from 'remotion';
import { interpolate } from 'remotion';

const rotation = spring(0, { mass: 1, damping: 100 });
const scale = spring(0, { mass: 1, damping: 100 });

const position = interpolate(0, 100, 0, { duration: 6 });

const iconLayer = (
  <g
    keyframes={{
      rotation: rotation,
      scale: scale,
    }}
  />
);

const textLayer = (
  <g
    keyframes={{
      position: position,
    }}
  />
);

const nullObject = (
  <g
    keyframes={{
      scale: spring(0, { mass: 1, damping: 100 }),
    }}
  />
);

return (
  <div>
    {iconLayer}
    {textLayer}
    {nullObject}
  </div>
);
```

This code uses the `spring` function from Remotion to create a bouncing animation for the rotation and scale of the icon layer, and the `interpolate` function to create a linear animation for the position of the text layer. The null object is used to create a zoom transition between the scenes.

**Recipe for the After Effects SaaS Tutorial**

**Scene 1:**

1. **Keyframe 1:**
	* Time: 0
	* Position: X = 0
2. **Keyframe 2:**
	* Time: 100
	* Position: X = 100
3. **Graph Editor:**
	* Ease: Linear
4. **Text Animator:**
	* Font: Arial
	* Size: 24
	* Color: Black
5. **Masks:**
	* None
6. **Camera/Null Move:**
	* Null object: Create a new null object and parent the screenshot to it.
	* Keyframe 1: Time = 0, Position = (0, 0)
	* Keyframe 2: Time = 100, Position = (-100, 0)
7. **Motion Blur:**
	* Enabled: Yes
8. **Glow:**
	* Enabled: No
9. **Transitions:**
	* None
10. **UI Mockup Handling:**
	* None

**Scene 2:**

1. **Background Animation:**
	* Turbulent Displace: Add a Turbulent Displace effect to the screenshot.
	* Evolution: Keyframe 1 = 0, Keyframe 2 = 60
2. **Shape Layer:**
	* Create a new circle shape layer.
	* Center the anchor point.
	* Scale: Keyframe 1 = 0, Keyframe 2 = 100
3. **Tracking:**
	* Track the shape layer with the screenshot.
4. **Opacity:**
	* 50% or 40%
5. **Fast Box Blur:**
	* Enabled: Yes
	* Radius: Increase the radius

**Scene 3:**

1. **Animation:**
	* Parent the shape layer with the screenshot.
	* Change the position of the screenshot.
	* Play with the scale.
2. **Text Layer:**
	* Add a new text layer.
	* Parent the text layer with the screenshot.
	* Change the position of the text layer.
3. **Position Keyframes:**
	* Keyframe 1: Time = 0, Position = (0, 0)
	* Keyframe 2: Time = 100, Position = (100, 0)

**Scene 4:**

1. **Transition:**
	* Move the screenshot to the left side.
	* Create a new null object and parent the screenshot to it.
	* Keyframe 1: Time = 0, Position = (0, 0)
	* Keyframe 2: Time = 100, Position = (-100, 0)
2. **Marker:**
	* Add a marker for this scene.
3. **Trimming:**
	* Trim the scene at the cut.

**Reproducing in Remotion (Code-Level)**

**Scene 1:**

```jsx
import { spring } from 'remotion';

const x = spring(0, {
  fps: 60,
  mass: 1,
  tension: 300,
  friction: 40,
});

return (
  <div>
    <div style={{ position: 'absolute', left: x }} />
  </div>
);
```

**Scene 2:**

```jsx
import { interpolate } from 'remotion';

const evolution = interpolate(0, 60, {
  easing: 'linear',
});

return (
  <div>
    <div
      style={{
        position: 'absolute',
        left: evolution,
        top: evolution,
      }}
    />
  </div>
);
```

**Scene 3:**

```jsx
import { spring } from 'remotion';

const x = spring(0, {
  fps: 60,
  mass: 1,
  tension: 300,
  friction: 40,
});

return (
  <div>
    <div style={{ position: 'absolute', left: x, top: x }} />
  </div>
);
```

**Scene 4:**

```jsx
import { spring } from 'remotion';

const x = spring(0, {
  fps: 60,
  mass: 1,
  tension: 300,
  friction: 40,
});

return (
  <div>
    <div style={{ position: 'absolute', left: x, top: x }} />
  </div>
);
```

Note that the code above is a simplified representation of the recipe and may require additional modifications to work as intended in a Remotion project.

**Recipe for the After Effects SaaS Tutorial**

**Scene 1: Two Views**

1. Create a new composition with the following settings:
	* Resolution: 1080p
	* Frame Rate: 60fps
	* Duration: 10 seconds
2. Import the screenshots and arrange them in a 3D space:
	* Select the top screenshot and place it around the center of the composition.
	* Play with the Y-axis to create 3D depth.
	* Select the second screenshot and move it in Z-space.
	* Change the X and Y positions of the second screenshot.
	* Repeat the process for the third screenshot.
3. Add a shadow effect to all the screenshots:
	* Create a new shape layer and make a perfect circle by holding shift.
	* Change the color to green.
	* Place the shape layer behind the screenshots and parent it with each screenshot.
	* Move the shape layer by one pixel and adjust the size.
	* Duplicate the shape layer and parent it with the next screenshot.
4. Add a fast box blur effect to the shape layer:
	* Select the shape layer and add a fast box blur effect.
	* Play with the radius to achieve the desired effect.

**Scene 2: Camera and Null**

1. Create a new camera and place it onto the active scene.
2. Add a new null object to control the camera.
3. Parent the camera with the null object and enable 3D.
4. Trim the camera and null object:
	* Select the null object and press P for position.
	* Make an empty keyframe and change the X position to around the center of the composition.
	* Select the keyframes and press F9 to make a smooth graph.
	* Add a marker at the starting point.
	* Adjust the keyframes to create a smooth animation.
5. Duplicate the text layers:
	* Select the text layers and press Control Shift D to duplicate.
	* Place the duplicated text layers at two.
	* Expand the text layers and place them here.

**Scene 3: Transition**

1. Add a transition for this scene:
	* Select the null object and press Control U to remove the keyframes.
	* Remove all the keyframes and parent the last null with the new null.
	* Press P for position and make an empty keyframe.
	* When the scene ends, zoom out the camera like this.
	* Select the keyframes and press F9 to make a smooth graph.
	* Trim the layers at this point and delete the unnecessary layers.

**Reproducing the Recipe in Remotion**

To reproduce the recipe in Remotion, you can use the following code:
```jsx
import { interpolate, spring } from 'remotion';

// Scene 1: Two Views

const screenshots = [
  { x: 100, y: 100, z: 0 },
  { x: 200, y: 200, z: 0 },
  { x: 300, y: 300, z: 0 },
];

const shadowLayers = [
  { x: 100, y: 100, z: 0, radius: 10 },
  { x: 200, y: 200, z: 0, radius: 10 },
  { x: 300, y: 300, z: 0, radius: 10 },
];

const cameraPosition = { x: 0, y: 0, z: 0 };

// Scene 2: Camera and Null

const nullObject = {
  x: 0,
  y: 0,
  z: 0,
};

const cameraKeyframes = [
  { time: 0, position: { x: 0, y: 0, z: 0 } },
  { time: 10, position: { x: -100, y: 0, z: 0 } },
];

const textLayers = [
  { x: 100, y: 100, z: 0 },
  { x: 200, y: 200, z: 0 },
  { x: 300, y: 300, z: 0 },
];

// Scene 3: Transition

const transitionKeyframes = [
  { time: 0, position: { x: 0, y: 0, z: 0 } },
  { time: 10, position: { x: -100, y: 0, z: 0 } },
];

export function TwoViews() {
  return (
    <div>
      <div style={{ position: 'absolute', top: 0, left: 0 }}>
        {screenshots.map((screenshot, index) => (
          <div
            key={index}
            style={{
              position: 'absolute',
              top: screenshot.y,
              left: screenshot.x,
              transform: `translate3d(0, 0, ${screenshot.z}px)`,
            }}
          >
            <img src={`screenshot${index + 1}.jpg`} />
          </div>
        ))}
      </div>
      <div style={{ position: 'absolute', top: 0, left: 0 }}>
        {shadowLayers.map((shadowLayer, index) => (
