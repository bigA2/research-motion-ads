# ruTR7i1oJgg
(source: transcript)

**Recipe for the Grid Animation in After Effects:**

1. **Composition Settings:**
	* Resolution: 4K
	* Frame Rate: 25 frames per second
	* Duration: Doesn't matter
2. **Background:**
	* Create a new solid layer (Layer > New > Solid)
	* Color: Almost white (click on the color picker and adjust to a light grayish tone)
	* Name: Background
3. **Grid:**
	* Create a new solid layer (Layer > New > Solid)
	* Color: Black
	* Name: Grid
	* Apply the "Grid" effect (Effects > Presets > Grid)
	* Adjust the grid settings:
		+ Color: Light grayish tone
		+ Size: Square grid
		+ Size: Bigger (around 100-150 pixels)
4. **Grid Feather:**
	* Select the Grid layer
	* Go to the Mask panel (Window > Mask)
	* Feather the edges of the grid:
		+ Feather: 10-20 pixels
		+ Expansion: 10-20 pixels
		+ Transparency: 50-70%
5. **Grid Selector:**
	* Create two new solid layers (Layer > New > Solid)
	* Color: Gray (darker tone)
	* Name: Grid Selector 1 and Grid Selector 2
	* Apply a stroke to both layers:
		+ Stroke: 5 pixels
		+ Color: Gray (darker tone)
	* Draw two rectangles:
		+ Grid Selector 1: Draw a rectangle (around 100-150 pixels)
		+ Grid Selector 2: Draw a rectangle (around 100-150 pixels)
	* Align both rectangles to the center of the composition:
		+ Vertically
		+ Horizontally
6. **Animation:**
	* Select the Grid Selector 1 layer
	* Open the Rectangle Path (Layer > Rectangle Path)
	* Unlink the size
	* Set a keyframe for the size:
		+ Beginning: Small size (around 50-70 pixels)
		+ Middle: Large size (around 100-150 pixels)
	* Repeat the same process for Grid Selector 2:
		+ Beginning: Small size (around 50-70 pixels)
		+ Middle: Large size (around 100-150 pixels)
	* Select both keyframes and apply a nice easing curve (Graph Editor > Ease Curve)
7. **Image in the Center:**
	* Go to the Project panel (Window > Project)
	* Double-click on an image (thumbnail)
	* Place the image in the center of the composition:
		+ Grid Selector 1: Center the image
		+ Grid Selector 2: Center the image

**Reproducing the Animation in Remotion:**

To reproduce the animation in Remotion, you'll need to write code that achieves the same effects. Here's a rough outline of how you can do it:

1. **Grid Animation:**
	* Create a `Grid` component with a `size` prop that animates from a small size to a large size.
	* Use the `interpolate` function to create a smooth animation curve.
	* Use the `spring` function to add a spring effect to the animation.
2. **Grid Selector Animation:**
	* Create a `GridSelector` component with a `size` prop that animates from a small size to a large size.
	* Use the `interpolate` function to create a smooth animation curve.
	* Use the `spring` function to add a spring effect to the animation.
3. **Image in the Center:**
	* Create an `Image` component and place it in the center of the composition.
	* Use the `position` prop to center the image horizontally and vertically.

Here's some sample code to get you started:
```jsx
import { interpolate, spring } from 'remotion';

const Grid = ({ size }) => {
  const animation = spring(size, {
    from: 50,
    to: 150,
    duration: 2,
  });

  return (
    <div
      style={{
        width: animation,
        height: animation,
        backgroundColor: 'lightgray',
      }}
    />
  );
};

const GridSelector = ({ size }) => {
  const animation = spring(size, {
    from: 50,
    to: 150,
    duration: 2,
  });

  return (
    <div
      style={{
        width: animation,
        height: animation,
        backgroundColor: 'gray',
        stroke: '5px',
        strokeColor: 'gray',
      }}
    />
  );
};

const Image = ({ position }) => {
  return (
    <img
      src="image.jpg"
      style={{
        position: 'absolute',
        top: position.top,
        left: position.left,
      }}
    />
  );
};

const App = () => {
  const animation = interpolate(0, 100, 150, {
    duration: 2,
  });

  return (
    <div>
      <Grid size={animation} />
      <GridSelector size={animation} />
      <Image position={{ top:

**Recipe:**

1. **Thumbnail Shape Layer**
	* Duplicate the thumbnail shape layer.
	* Go to the beginning of the duplicated shape layer.
	* Copy the rectangle path of the original shape layer.
	* Paste the copied path into the duplicated shape layer.
	* Merge the paths of the duplicated shape layer by selecting "Intersect".
	* Set the fill of the duplicated shape layer to black.
2. **Mat Effect**
	* Drag the thumbnail shape layer into the mat effect.
	* Turn the thumbnail back on.
3. **Scale Animation**
	* Press S for scale and set a keyframe.
	* Go a bit further and scale down.
	* Easy ease the scale animation.
4. **Blob Effect**
	* Create a new composition.
	* Go to layer, new, solid.
	* Add a bluish color to the solid layer.
	* Use the ellipse tool to create a blob shape.
	* Add a wiggle path to the blob shape.
	* Change the detail and size of the wiggle path.
	* Scale up the blob shape.
	* Add a fast box blur to the blob shape.
	* Duplicate the blob shape layer.
	* Scale down the duplicated blob shape layer.
	* Change the fill color of the duplicated blob shape layer.
	* Duplicate the blob shape layer again.
	* Move the duplicated blob shape layer down.
	* Change the fill color of the duplicated blob shape layer.
5. **Search Bar**
	* Create a new rounded rectangle shape.
	* Center the shape.
	* Change the fill color to a dark, almost black color.
	* Add a thin stroke to the shape.
	* Make the stroke dark.
	* Duplicate the shape layer.
	* Change the stroke to a linear gradient.
	* Make the gradient blue to transparent.
	* Turn the fill to none.
	* Increase the stroke size.
	* Rotate the gradient stroke.
	* Add a glow to the shape.

**Reproducing in Remotion:**

To reproduce the recipe in Remotion, you will need to write code that achieves the same effects. Here is a possible implementation:

```jsx
import { interpolate, spring } from 'remotion';

// Thumbnail Shape Layer
const thumbnailShapeLayer = () => {
  const path = [
    { x: 0, y: 0 },
    { x: 100, y: 0 },
    { x: 100, y: 100 },
    { x: 0, y: 100 },
    { x: 0, y: 0 },
  ];

  const mergedPath = path.map((point, index) => {
    if (index === 0) return point;
    const previousPoint = path[index - 1];
    return {
      x: previousPoint.x + (point.x - previousPoint.x) * 0.5,
      y: previousPoint.y + (point.y - previousPoint.y) * 0.5,
    };
  });

  return mergedPath;
};

// Mat Effect
const matEffect = () => {
  const thumbnailShapeLayerPath = thumbnailShapeLayer();
  return thumbnailShapeLayerPath;
};

// Scale Animation
const scaleAnimation = () => {
  const scale = spring(1, { damping: 100 });
  return scale;
};

// Blob Effect
const blobEffect = () => {
  const wigglePath = [
    { x: 0, y: 0 },
    { x: 100, y: 100 },
    { x: 200, y: 200 },
    { x: 300, y: 300 },
    { x: 400, y: 400 },
  ];

  const wiggledPath = wigglePath.map((point, index) => {
    if (index === 0) return point;
    const previousPoint = wigglePath[index - 1];
    return {
      x: previousPoint.x + (point.x - previousPoint.x) * 0.5,
      y: previousPoint.y + (point.y - previousPoint.y) * 0.5,
    };
  });

  return wiggledPath;
};

// Search Bar
const searchBar = () => {
  const roundedRectangleShape = [
    { x: 0, y: 0 },
    { x: 100, y: 0 },
    { x: 100, y: 100 },
    { x: 0, y: 100 },
    { x: 0, y: 0 },
  ];

  const linearGradient = [
    { x: 0, y: 0 },
    { x: 100, y: 0 },
    { x: 100, y: 100 },
    { x: 0, y: 100 },
    { x: 0, y: 0 },
  ];

  return roundedRectangleShape;
};

export default () => {
  const thumbnailShapeLayerPath = matEffect();
  const scale = scaleAnimation();
  const blobShapeLayerPath = blobEffect();
  const searchBarShape = searchBar();

  return (
    <div>
      <svg>
        <path d={thumbnailShapeLayerPath.join(' ')} />
        <path d={blobShapeLayerPath.join(' ')}

**Recipe:**

1. **Glow Effect:**
	* Duplicate the glow effect 3-4 times.
	* Set the glow radius to 100 for each duplicate.
	* Adjust the intensity of each glow to create a soft and subtle effect.
	* Change the color of the glow to a flat, luxurious color (e.g. #333333).
2. **Text Typing:**
	* Create a new text layer and type the desired text.
	* Apply the typewriter effect by going to Effects > Presets > Typewriter.
	* Adjust the text color to a desired color (e.g. #FFFFFF).
	* Change the text alignment to center or left, depending on the desired effect.
3. **Animation:**
	* Link the search bar and text layers together by duplicating the rectangle path and linking the size.
	* Parent the glow and text layers to the shape layer.
	* Add keyframes for the size, scale, and rotation of the shape layer.
	* Apply a bounce effect to the keyframes using the Full Stack Editor plugin or by copying and pasting an expression.
	* Fade in the layers by adjusting the transparency keyframes.
4. **Null Object:**
	* Create a new null object and link the shape layer to it.
	* Press S for scale and P for position, and then scale up the null object and move its position.
	* Select the keyframes, right-click, and toggle hold keyframe.
	* Move the text layer with the null object by adjusting its position keyframes.
5. **Image Orbit:**
	* Create a new composition and import the desired images.
	* Create a new null object and link the image layer to it.
	* Press S for scale and P for position, and then scale up the null object and move its position.
	* Select the keyframes, right-click, and toggle hold keyframe.
	* Move the image layer with the null object by adjusting its position keyframes.

**Settings:**

* Glow Effect:
	+ Glow radius: 100
	+ Intensity: Adjusted to create a soft and subtle effect
	+ Color: #333333
* Text Typing:
	+ Text color: #FFFFFF
	+ Text alignment: Center or left
* Animation:
	+ Keyframe timings: 0-100 frames
	+ Easing: Bounce effect applied using the Full Stack Editor plugin or by copying and pasting an expression
	+ Transparency: Adjusted to fade in the layers
* Null Object:
	+ Scale: 100%
	+ Position: Adjusted to move the null object
* Image Orbit:
	+ Scale: 100%
	+ Position: Adjusted to move the null object

**Remotion Code:**

```jsx
import { interpolate, spring } from 'remotion';

const glowRadius = 100;
const intensity = 0.5;
const color = '#333333';

const textTyping = {
  color: '#FFFFFF',
  alignment: 'center',
};

const animation = {
  keyframeTimings: [0, 100],
  easing: spring(100),
  transparency: 0,
};

const nullObject = {
  scale: 100,
  position: [0, 0],
};

const imageOrbit = {
  scale: 100,
  position: [0, 0],
};

function GlowEffect() {
  const radius = interpolate(animation.keyframeTimings, [0, 100], [glowRadius, 0]);
  const intensityValue = interpolate(animation.keyframeTimings, [0, 100], [intensity, 0]);
  const colorValue = interpolate(animation.keyframeTimings, [0, 100], [color, '#FFFFFF']);

  return (
    <div
      style={{
        glowRadius: radius,
        intensity: intensityValue,
        color: colorValue,
      }}
    />
  );
}

function TextTyping() {
  const colorValue = interpolate(animation.keyframeTimings, [0, 100], [textTyping.color, '#FFFFFF']);
  const alignmentValue = interpolate(animation.keyframeTimings, [0, 100], [textTyping.alignment, 'left']);

  return (
    <div
      style={{
        color: colorValue,
        textAlign: alignmentValue,
      }}
    />
  );
}

function Animation() {
  const keyframeTimings = animation.keyframeTimings;
  const easing = animation.easing;
  const transparency = animation.transparency;

  return (
    <div
      style={{
        opacity: transparency,
      }}
    />
  );
}

function NullObject() {
  const scale = nullObject.scale;
  const position = nullObject.position;

  return (
    <div
      style={{
        transform: `scale(${scale})`,
        transformOrigin: position,
      }}
    />
  );
}

function ImageOrbit() {
  const scale = imageOrbit.scale;
  const position = imageOrbit.position;

  return (
    <div
      style={{
        transform: `scale(${scale})`,
        transformOrigin: position,
      }}
    />
  );
}
```

Note that this code uses the `remotion` library to create the animation and apply the effects. The `interpolate` function is used

**Recipe:**

1. **Importing Images**
	* Import 3 images by dragging and dropping them into After Effects.
2. **Running Script**
	* Go to File > Scripts > Run Script File.
	* Select the Tom's Project Orbit script.
3. **Creating Orbit**
	* Select the layers.
	* Hit Create Orbit.
	* Choose a shape (e.g., circle).
4. **Adjusting Animation**
	* Hit U to reveal the animation.
	* Move the animation to the left.
	* Go into the graph editor and make the animation smoother.
5. **Customizing Orbit**
	* Go into the null and change the scale.
	* Press S to scale the orbit path.
	* Change the spacing between the images.
6. **Making it 3D**
	* Turn the orbit path into 3D.
	* Change the X rotation.
	* Set a keyframe on the Y rotation.
7. **Adjusting Speed**
	* Set the speed to 70.
	* Remove travel keyframes.

**Settings:**

* Keyframe timings: 
	+ Move animation to the left at frame 100.
	+ Make animation smoother at frame 150.
	+ Change scale at frame 200.
	+ Change spacing at frame 250.
	+ Set keyframe on Y rotation at frame 300.
* Easing/graph editor values: 
	+ Ease in/out at 50% at frame 150.
* Text animator setup: None.
* Masks: None.
* Camera/null moves: 
	+ Change scale at frame 200.
	+ Change spacing at frame 250.
* Motion blur: None.
* Glow: None.
* Transitions: None.
* UI mockup handling: None.
* Typography sizes/fonts: None.
* Background animation: None.
* Sound: None.

**Reproducing in Remotion:**

Here's a code-level example of how to reproduce this in Remotion:

```jsx
import { interpolate, spring } from 'remotion';

const animation = spring({
  from: 0,
  to: 1,
  duration: 200,
  easing: 'easeInOut',
});

const orbitPath = {
  x: interpolate(0, animation),
  y: interpolate(0, animation),
};

const images = [
  {
    x: interpolate(0, animation),
    y: interpolate(0, animation),
  },
  {
    x: interpolate(0, animation),
    y: interpolate(0, animation),
  },
  {
    x: interpolate(0, animation),
    y: interpolate(0, animation),
  },
];

const nullScale = spring({
  from: 1,
  to: 2,
  duration: 250,
  easing: 'easeInOut',
});

const spacing = spring({
  from: 0,
  to: 100,
  duration: 250,
  easing: 'easeInOut',
});

const yRotation = spring({
  from: 0,
  to: 90,
  duration: 300,
  easing: 'easeInOut',
});

return (
  <div>
    <div
      style={{
        transform: `translate(${orbitPath.x}px, ${orbitPath.y}px)`,
        scale: nullScale.value,
      }}
    >
      {images.map((image, index) => (
        <div
          key={index}
          style={{
            transform: `translate(${image.x}px, ${image.y}px)`,
            spacing: spacing.value,
          }}
        >
          {/* Image content */}
        </div>
      ))}
    </div>
    <div
      style={{
        transform: `rotateY(${yRotation.value}deg)`,
      }}
    >
      {/* Content */}
    </div>
  </div>
);
```

Note that this is a simplified example and may not exactly replicate the After Effects animation.
