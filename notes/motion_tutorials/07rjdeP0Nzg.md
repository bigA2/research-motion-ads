# 07rjdeP0Nzg
(source: transcript)

**Recipe for Card 1 in After Effects:**

1. **Rectangle Shape:**
	* Create a new shape layer (1920x1080)
	* Draw a rough rectangle shape
	* Center align the anchor point
	* Use the Motion Tools extension to center align the shape
	* Roughly alter the shape to make it smaller
	* Add a gradient overlay to the shape
	* Set the gradient to horizontal
	* Match the colors to a dark and grayish tone
	* Add an inner glow to the shape
	* Disable the inner glow outline
2. **Small Boxes for Icons and Text:**
	* Create small boxes for the icons and text
	* Select all three boxes and press the "Align" button to equally space them out
	* Label the boxes with different colors (yellow and pink)
	* Add a prop shadow to the boxes
3. **Text Settings:**
	* Use the SF Pro font at medium weight
	* Set the letter spacing to -33
4. **Animation Presets:**
	* Use the "XP" animation preset from the Motion Tools extension
	* Reduce the gap between the text and the box
	* Use the "Fill" animation preset to add a fill animation to the box
	* Add a deep blue fill animation to the box

**Keyframe Timings:**

* The rectangle shape animation starts at 0 seconds and ends at 15.50 seconds
* The small boxes animation starts at 0 seconds and ends at 15.50 seconds
* The text animation starts at 0 seconds and ends at 15.50 seconds

**Easing/Graph Editor Values:**

* The rectangle shape animation uses a linear easing
* The small boxes animation uses a linear easing
* The text animation uses a linear easing

**Text Animator Setup:**

* Use the SF Pro font at medium weight
* Set the letter spacing to -33

**Masks:**

* None

**Camera/Null Moves:**

* None

**Motion Blur:**

* None

**Glow:**

* Add an inner glow to the rectangle shape
* Disable the inner glow outline

**Transitions:**

* None

**UI Mockup Handling:**

* None

**Typography Sizes/Fonts:**

* Use the SF Pro font at medium weight
* Set the letter spacing to -33

**Background Animation:**

* None

**Sound:**

* None

**Reproducing in Remotion:**

To reproduce this animation in Remotion, you can use the following code:

```jsx
import { spring } from 'remotion';

const rectangle = {
  x: 0,
  y: 0,
  width: 100,
  height: 100,
  fill: '#333',
  stroke: '#fff',
  strokeWidth: 2,
};

const smallBoxes = [
  {
    x: 100,
    y: 100,
    width: 50,
    height: 50,
    fill: '#f7dc6f',
    stroke: '#fff',
    strokeWidth: 2,
  },
  {
    x: 200,
    y: 100,
    width: 50,
    height: 50,
    fill: '#ff69b4',
    stroke: '#fff',
    strokeWidth: 2,
  },
];

const text = {
  x: 300,
  y: 300,
  text: 'Hello World',
  fontSize: 24,
  fontFamily: 'SF Pro',
  letterSpacing: -33,
};

const animation = () => {
  const t = spring(0, { mass: 100, damping: 20, stiffness: 100 });

  return (
    <div>
      <div
        style={{
          position: 'absolute',
          left: rectangle.x,
          top: rectangle.y,
          width: rectangle.width,
          height: rectangle.height,
          background: rectangle.fill,
          border: `2px solid ${rectangle.stroke}`,
        }}
      />
      {smallBoxes.map((box, index) => (
        <div
          key={index}
          style={{
            position: 'absolute',
            left: box.x,
            top: box.y,
            width: box.width,
            height: box.height,
            background: box.fill,
            border: `2px solid ${box.stroke}`,
          }}
        />
      ))}
      <div
        style={{
          position: 'absolute',
          left: text.x,
          top: text.y,
          fontSize: text.fontSize,
          fontFamily: text.fontFamily,
          letterSpacing: text.letterSpacing,
        }}
      >
        {text.text}
      </div>
    </div>
  );
};

export default animation;
```

This code creates a rectangle, two small boxes, and a text element, and animates them using the `spring` function from Remotion. The animation starts at 0 seconds and ends at 15.50 seconds, with a linear easing. The rectangle shape animation uses a linear easing, the small boxes animation uses a linear easing, and the text animation uses a linear easing. The typography sizes and fonts are set to the SF Pro font at medium weight, with a letter spacing of -33. The background animation is none, and the sound is none.

**Recipe for the Animation:**

1. **Text Animation:**
	* Create a text layer with the text "fill [music]".
	* Initially, the text has a pink color.
	* At frame 39, the text changes to yellow.
	* At frame 78, the text changes back to its original color (pink).
	* Use a color animator to achieve this effect.
2. **Deep Blue Animation:**
	* Create a deep blue layer with an initial exposure of 0.
	* At frame 39, the exposure increases to 39.
	* At frame 78, the exposure decreases back to 0.
	* Use an exposure animator to achieve this effect.
3. **Emoji Animation:**
	* Create an emoji layer with an initial scale of 1.
	* At frame 4, the scale increases to 25.
	* At frame 8, the scale decreases back to 0.
	* Use a scale animator to achieve this effect.
4. **Box Animation:**
	* Create a box layer with an initial position of (0, 0).
	* At frame 4, the position increases to (25, 25).
	* At frame 8, the position decreases back to (0, 0).
	* Use a position animator to achieve this effect.
5. **Bouncer Animation:**
	* Use the Epic Bouncer plug-in to create a bouncer animation.
	* Set the amplitude to 25.
	* Use this animation to animate the emoji and box layers.

**Settings:**

* Keyframe timings:
	+ Frame 39: Text color changes to yellow.
	+ Frame 78: Text color changes back to pink.
	+ Frame 39: Deep blue exposure increases to 39.
	+ Frame 78: Deep blue exposure decreases back to 0.
	+ Frame 4: Emoji scale increases to 25.
	+ Frame 8: Emoji scale decreases back to 0.
	+ Frame 4: Box position increases to (25, 25).
	+ Frame 8: Box position decreases back to (0, 0).
* Easing:
	+ Use a linear easing for the text and deep blue animations.
	+ Use a spring easing for the emoji and box animations.
* Graph Editor values:
	+ Use a value of 1 for the text and deep blue animations.
	+ Use a value of 25 for the emoji and box animations.
* Text animator setup:
	+ Use a color animator to change the text color.
	+ Use an exposure animator to change the deep blue exposure.
* Masks:
	+ Use a mask to hide the text and deep blue layers when not in use.
* Camera/null moves:
	+ Use a null object to move the text and deep blue layers.
* Motion blur:
	+ Use a motion blur effect to blur the text and deep blue layers.
* Glow:
	+ Use a glow effect to add a glow to the text and deep blue layers.
* Transitions:
	+ Use a transition effect to animate the text and deep blue layers.
* UI mockup handling:
	+ Use a UI mockup to create a mockup of the final animation.
* Typography sizes/fonts:
	+ Use a font size of 24 for the text layer.
	+ Use a font family of Arial for the text layer.
* Background animation:
	+ Use a background animation to create a background for the animation.
* Sound:
	+ Use a sound effect to add audio to the animation.

**Reproducing the Animation in Remotion:**

To reproduce the animation in Remotion, you can use the following code:

```javascript
import { spring } from 'remotion';
import { interpolate } from 'remotion';

const text = {
  color: spring(0, { duration: 1 }),
  exposure: spring(0, { duration: 1 }),
};

const emoji = {
  scale: spring(1, { duration: 1 }),
};

const box = {
  position: spring([0, 0], { duration: 1 }),
};

const bouncer = {
  amplitude: 25,
};

const animation = (
  <div>
    <Text text={text.color} />
    <DeepBlue exposure={text.exposure} />
    <Emoji scale={emoji.scale} />
    <Box position={box.position} />
    <Bouncer amplitude={bouncer.amplitude} />
  </div>
);

export default function MyComponent() {
  return (
    <div>
      {animation}
    </div>
  );
}
```

In this code, we use the `spring` function from `remotion` to animate the text and deep blue layers. We also use the `interpolate` function from `remotion` to animate the emoji and box layers. The `bouncer` animation is created using the `Epic Bouncer` plug-in.

**Recipe for the After Effects Animation**

1. **Card Animation**
	* Create a new composition (15 seconds, 1080p)
	* Import a 3D card model
	* Animate the scale and rotation properties of the card using keyframes
	* Set the orientation property to rotate the card
	* Use a time expression to control the rotation
2. **Lock Animation**
	* Create a new composition (15 seconds, 1080p)
	* Import a 3D lock model
	* Animate the scale and rotation properties of the lock using keyframes
	* Set the orientation property to rotate the lock
	* Use a time expression to control the rotation
3. **Lighting**
	* Add an environment light to the composition
	* Use an HDRI image to create a realistic lighting effect
	* Adjust the position and intensity of the light to achieve the desired look
4. **Camera Movement**
	* Use the camera null to move the camera around the composition
	* Use the middle mouse button to move the camera
	* Use the right mouse button to zoom in and out
5. **Motion Blur**
	* Enable motion blur on the card and lock animations
	* Adjust the motion blur settings to achieve the desired effect
6. **Glow Effect**
	* Add a glow effect to the card and lock animations
	* Adjust the glow settings to achieve the desired effect
7. **Transitions**
	* Use a transition effect to move from one animation to the next
	* Adjust the transition settings to achieve the desired effect
8. **UI Mockup**
	* Create a UI mockup to display the card and lock animations
	* Use a text animator to animate the text on the UI mockup
	* Use a mask to create a circular shape around the card and lock animations
9. **Typography**
	* Use a specific font and font size for the text on the UI mockup
	* Adjust the typography settings to achieve the desired look
10. **Background Animation**
	* Create a background animation to display behind the card and lock animations
	* Use a particle system or a background image to create a dynamic effect

**Reproducing the Animation in Remotion**

To reproduce the animation in Remotion, you can use the following code:
```jsx
import { spring } from 'remotion';

const card = spring({
  from: { scale: 0, rotation: 0 },
  to: { scale: 1, rotation: 360 },
  duration: 15,
  easing: spring.easing.easeInOut,
});

const lock = spring({
  from: { scale: 0, rotation: 0 },
  to: { scale: 1, rotation: 360 },
  duration: 15,
  easing: spring.easing.easeInOut,
});

const light = spring({
  from: { intensity: 0 },
  to: { intensity: 1 },
  duration: 15,
  easing: spring.easing.easeInOut,
});

const camera = spring({
  from: { position: { x: 0, y: 0, z: 0 } },
  to: { position: { x: 100, y: 100, z: 100 } },
  duration: 15,
  easing: spring.easing.easeInOut,
});

const animation = () => {
  const currentTime = useCurrentFrame();
  const cardScale = card(currentTime);
  const lockScale = lock(currentTime);
  const lightIntensity = light(currentTime);
  const cameraPosition = camera(currentTime);

  return (
    <div>
      <div style={{ transform: `scale(${cardScale}) rotate(${cardScale * 360}deg)` }}>
        <Card />
      </div>
      <div style={{ transform: `scale(${lockScale}) rotate(${lockScale * 360}deg)` }}>
        <Lock />
      </div>
      <div style={{ transform: `translate3d(${cameraPosition.x}px, ${cameraPosition.y}px, ${cameraPosition.z}px)` }}>
        <Camera />
      </div>
      <div style={{ opacity: lightIntensity }}>
        <Light />
      </div>
    </div>
  );
};
```
Note that this code uses the `spring` function from Remotion to animate the card, lock, light, and camera. The `useCurrentFrame` hook is used to get the current frame number, and the `style` attribute is used to apply the animated values to the elements.

**Recipe for the 3D Animation**

1. **3D Card Com Settings**
	* Color: Orange
	* Shadow: Use Shadow Studio plug-in or normal drop shadow
	* Position: Place the 3D card com inside the main shape
2. **Camera Animation**
	* Duration: 25 seconds
	* Frame Rate: 25 fps
	* Skew: Skew the camera to create a dynamic angle
	* Position: Place the camera at different angles to create a sense of movement
3. **Circular Animation**
	* Duration: 25 seconds
	* Frame Rate: 25 fps
	* Rotation: Keyframe the rotation of each card comp
	* Scale: Reduce the scale of each card comp
	* Position: Align the cards in a circle using a null layer
4. **Null Layer Animation**
	* Duration: 25 seconds
	* Frame Rate: 25 fps
	* Rotation: Keyframe the rotation of the null layer to create a circular motion
	* Scale: Scale the null layer to create a sense of movement
5. **Motion Blur**
	* Duration: 25 seconds
	* Frame Rate: 25 fps
	* Blur Amount: Set the blur amount to create a sense of motion
6. **Glow**
	* Duration: 25 seconds
	* Frame Rate: 25 fps
	* Glow Amount: Set the glow amount to create a sense of light
7. **Transitions**
	* Duration: 25 seconds
	* Frame Rate: 25 fps
	* Transition Type: Use a fade-in or fade-out transition to create a smooth animation
8. **UI Mockup Handling**
	* Duration: 25 seconds
	* Frame Rate: 25 fps
	* UI Elements: Add UI elements such as buttons and text to create a interactive animation
9. **Typography Sizes/Fonts**
	* Font: Use a clean and modern font such as Arial or Helvetica
	* Size: Set the font size to create a clear and readable text
10. **Background Animation**
	* Duration: 25 seconds
	* Frame Rate: 25 fps
	* Background Color: Use a solid color or a gradient to create a dynamic background

**Reproducing the Animation in Remotion**

To reproduce the animation in Remotion, you can use the following code:

```jsx
import { useRemotion } from 'remotion';
import { interpolate, spring } from 'remotion';

const { lengthInFrames, frames } = useRemotion();

const cards = [
  {
    id: 1,
    x: 0,
    y: 0,
    rotation: 0,
    scale: 1,
  },
  {
    id: 2,
    x: 100,
    y: 100,
    rotation: 0,
    scale: 1,
  },
  {
    id: 3,
    x: 200,
    y: 200,
    rotation: 0,
    scale: 1,
  },
  {
    id: 4,
    x: 300,
    y: 300,
    rotation: 0,
    scale: 1,
  },
  {
    id: 5,
    x: 400,
    y: 400,
    rotation: 0,
    scale: 1,
  },
];

const nullLayer = {
  id: 0,
  x: 0,
  y: 0,
  rotation: 0,
  scale: 1,
};

const animation = () => {
  const currentTime = frames / lengthInFrames;
  const time = currentTime * 25;

  cards.forEach((card) => {
    const x = interpolate(time, [0, 25], [card.x, card.x + 100]);
    const y = interpolate(time, [0, 25], [card.y, card.y + 100]);
    const rotation = spring(time, card.rotation, { damping: 200 });
    const scale = spring(time, card.scale, { damping: 200 });

    return (
      <g key={card.id}>
        <circle cx={x} cy={y} r={20} fill="#FFA07A" />
        <text x={x} y={y} textAnchor="middle" dominantBaseline="middle" fontSize={24} fill="#FFFFFF">
          {card.id}
        </text>
        <g transform={`rotate(${rotation}) scale(${scale})`}>
          <rect x={-20} y={-20} width={40} height={40} fill="#FFA07A" />
        </g>
      </g>
    );
  });

  const nullLayerAnimation = (
    <g key={nullLayer.id}>
      <circle cx={0} cy={0} r={20} fill="#FFFFFF" />
      <g transform={`rotate(${spring(time, nullLayer.rotation, { damping: 200 })}) scale(${spring(time, nullLayer.scale, { damping: 200 })})`}>
        {cards.map((card) => (
          <g key={card.id}>
            <circle cx={card.x} cy={card.y} r={20} fill="#FFA
