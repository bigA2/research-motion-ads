# Jccbzpicst8
(source: transcript)

**Recipe for the Scene**

1. **Composition Settings**
	* Resolution: 4K
	* Frame Rate: 25 frames per second
	* Duration: 1 minute
2. **Background**
	* Create a new solid layer
	* Set the color to a four-color gradient
	* Pick the colors: off-white, light bluish, and a bit less bluish
	* Set the blend mode to a lot
	* Set the jitter to 100% to avoid banding
3. **UI**
	* Create a new rounded rectangle
	* Set the fill to fully white
	* Add a stroke to the rectangle
	* Set the stroke color to a light grayish color
	* Set the roundness to 60
	* Add a drop shadow to the rectangle
		+ Set the size to a lot
		+ Set the angle to 90°
		+ Set the distance to a bit below the rectangle
		+ Set the opacity to 5%
4. **Memoji**
	* Import a Memoji
	* Scale the Memoji down a bit
	* Create a new ellipse
	* Set the stroke to none
	* Add a linear gradient fill to the ellipse
	* Use the same colors as the background
5. **Animation**
	* Set the animation to start at frame 0
	* Set the animation to end at frame 60
	* Use a spring easing to make the animation smooth

**Keyframe Timings**

* Frame 0: Start of the animation
* Frame 60: End of the animation

**Easing/Graph Editor Values**

* Spring easing: 0.5, 0.5, 0.5, 0.5

**Text Animator Setup**

* None

**Masks**

* None

**Camera/Null Moves**

* None

**Motion Blur**

* None

**Glow**

* None

**Transitions**

* None

**UI Mockup Handling**

* None

**Typography Sizes/Fonts**

* None

**Background Animation**

* None

**Sound**

* None

**Reproducing in Remotion**

To reproduce this scene in Remotion, you would need to write the following code:

```jsx
import { useRemotion } from 'remotion';
import { interpolate, spring } from 'remotion';

const { frames } = useRemotion();

const background = {
  color: interpolate(frames, [0, 60], ['#ffffff', '#ffffff'], {
    easing: spring(0.5, 0.5, 0.5, 0.5),
  }),
};

const ui = {
  fill: interpolate(frames, [0, 60], ['#ffffff', '#ffffff'], {
    easing: spring(0.5, 0.5, 0.5, 0.5),
  }),
  stroke: interpolate(frames, [0, 60], ['#cccccc', '#cccccc'], {
    easing: spring(0.5, 0.5, 0.5, 0.5),
  }),
};

const memoji = {
  scale: interpolate(frames, [0, 60], [1, 1], {
    easing: spring(0.5, 0.5, 0.5, 0.5),
  }),
};

const ellipse = {
  fill: interpolate(frames, [0, 60], ['#ffffff', '#ffffff'], {
    easing: spring(0.5, 0.5, 0.5, 0.5),
  }),
};

export default function MyComposition() {
  return (
    <div>
      <div
        style={{
          backgroundColor: background.color,
          position: 'absolute',
          top: 0,
          left: 0,
          width: '100%',
          height: '100%',
        }}
      />
      <div
        style={{
          position: 'absolute',
          top: 100,
          left: 100,
          width: 200,
          height: 200,
          backgroundColor: ui.fill,
          border: `1px solid ${ui.stroke}`,
          borderRadius: 60,
          boxShadow: '0 0 10px rgba(0, 0, 0, 0.1)',
        }}
      />
      <div
        style={{
          position: 'absolute',
          top: 300,
          left: 300,
          width: 100,
          height: 100,
          backgroundImage: `linear-gradient(to bottom, ${ui.stroke}, ${ui.stroke})`,
        }}
      />
      <div
        style={{
          position: 'absolute',
          top: 400,
          left: 400,
          width: 50,
          height: 50,
          backgroundColor: memoji.scale,
          borderRadius: 25,
        }}
      />
      <div
        style={{
          position: 'absolute',
          top: 500,
          left: 500,
          width: 50,
          height: 50,
          backgroundImage: `linear-gradient(to bottom, ${ellipse.fill}, ${ellipse.fill})`,
        }}
      />
    </div>
  );
}
```

This code uses the `useRemotion` hook to get the

**Recipe for the After Effects Animation**

1. **Crop the shape**: Scale up the shape so the bottom hits the bottom of the ellipse (frame 0).
2. **Parent the ellipse to the shape**: Parent the ellipse to the shape (frame 0).
3. **Scale down the ellipse**: Scale down the ellipse to a small size (frame 0).
4. **Add text**: Add text to the composition using the text tool (frame 0).
5. **Style the text**: Make the text color off-black (frame 0).
6. **Duplicate the text**: Duplicate the text and add a subtitle (frame 0).
7. **Style the subtitle**: Make the subtitle smaller and thinner (frame 0).
8. **Create a button**: Create a rounded rectangle and style it with a soft gradient (frame 0).
9. **Add a glow effect**: Add an inner glow effect to the button (frame 0).
10. **Center the elements**: Center the elements in the composition (frame 0).
11. **Duplicate the title**: Duplicate the title and move it above the button (frame 0).
12. **Style the title**: Make the title white and fully white (frame 0).

**Animation Settings**

1. **Zoom out animation**: Create a new null object and parent all layers except the PNG to it (frame 0).
2. **Scale the null object**: Scale the null object to zoom out from the card (frame 0).
3. **Easy ease the keyframes**: Easy ease the keyframes for the scale animation (frame 0).
4. **Enable motion blur**: Enable motion blur on all layers (frame 0).
5. **Animate the elements**: Animate the elements in the composition (frame 0).

**Keyframe Timings**

1. **Zoom out animation**: Frame 0-100 (scale from 1 to 10)
2. **Scale the null object**: Frame 0-100 (scale from 1 to 10)
3. **Easy ease the keyframes**: Frame 0-100 (easy ease the keyframes)
4. **Animate the elements**: Frame 0-100 (animate the elements)

**Easing/Graph Editor Values**

1. **Easy ease the keyframes**: Graph editor value: 0.5 (easy ease the keyframes)
2. **Animate the elements**: Graph editor value: 0.5 (animate the elements)

**Text Animator Setup**

1. **Text color**: Off-black (frame 0)
2. **Subtitle size**: Smaller and thinner (frame 0)
3. **Title color**: White and fully white (frame 0)

**Masks**

1. **Ellipse mask**: Create a mask using the ellipse (frame 0)
2. **Button mask**: Create a mask using the button (frame 0)

**Camera/Null Moves**

1. **Null object**: Create a new null object and parent all layers except the PNG to it (frame 0)
2. **Scale the null object**: Scale the null object to zoom out from the card (frame 0)

**Motion Blur**

1. **Enable motion blur**: Enable motion blur on all layers (frame 0)

**Glow**

1. **Inner glow effect**: Add an inner glow effect to the button (frame 0)

**Transitions**

1. **None**: No transitions used in this animation

**UI Mockup Handling**

1. **Center the elements**: Center the elements in the composition (frame 0)
2. **Duplicate the title**: Duplicate the title and move it above the button (frame 0)

**Typography Sizes/Fonts**

1. **Title font**: [font name] (frame 0)
2. **Subtitle font**: [font name] (frame 0)
3. **Button font**: [font name] (frame 0)

**Background Animation**

1. **None**: No background animation used in this animation

**Sound**

1. **None**: No sound used in this animation

**Reproducing the Animation in Remotion**

To reproduce the animation in Remotion, you can use the following code:

```jsx
import { interpolate, spring } from 'remotion';

const zoomOutAnimation = (t) => {
  return spring(t, {
    mass: 300,
    damping: 40,
    stiffness: 100,
    overshootClamping: true,
    restDisplacementThreshold: 0.001,
    restSpeedThreshold: 0.001,
  });
};

const animateElements = (t) => {
  return spring(t, {
    mass: 300,
    damping: 40,
    stiffness: 100,
    overshootClamping: true,
    restDisplacementThreshold: 0.001,
    restSpeedThreshold: 0.001,
  });
};

const zoomOut = (t) => {
  return zoomOutAnimation(t);
};

const animateElements = (t) => {
  return animateElements(t);
};

export const ZoomOut = ({ t }) => {
  const zoomOutValue = zoomOut(t);
  const animateElementsValue = animateElements(t);

  return (
    <div>
      <div
        style={{
          transform: `scale(${zoomOutValue})`,
          transition: 'transform 1s

**Recipe for the Animation**

1. **Text Animation**
	* Select the text layer and go to the Text Animator panel.
	* Add a new Text Animator by clicking on the "+" button.
	* Set the Text Animator to "Position" and move the position to 50 and opacity to zero.
	* Set the "Based on" to "Words" and the "Shape" to "Ramp Up".
	* Set the "Ease" to 100% and keyframe the offset by clicking on the stopwatch next to the offset.
	* Set the offset to -100% and then to 100%.
2. **Shape Animation**
	* Select the shape layer and go to the Shape Rectangle panel.
	* Animate the size and roundness of the shape.
	* Set a keyframe for the scale and then set it to zero.
	* Use the Graph Editor to make the animation smooth.
3. **Background Animation**
	* Duplicate the shape layer and scale it up.
	* Set a keyframe for the scale and then scale it down.
	* Use the Graph Editor to make the animation smooth.
	* Offset the keyframes to create a sense of movement.
4. **Cursor Animation**
	* Import a cursor shape and animate its position and scale.
	* Use the Convert Vertex tool to make the path organic.
	* Easy ease the animation in the Graph Editor.

**Settings**

* Text Animator:
	+ Based on: Words
	+ Shape: Ramp Up
	+ Ease: 100%
	+ Offset: -100% to 100%
* Shape Rectangle:
	+ Size: Animate
	+ Roundness: Animate
	+ Scale: Set to zero
* Background Animation:
	+ Scale: Set to zero
	+ Offset: Create a sense of movement
* Cursor Animation:
	+ Position: Animate
	+ Scale: Animate
	+ Convert Vertex tool: Make the path organic

**Remotion Code**

```javascript
import { interpolate, spring } from 'remotion';

// Text Animation
const textAnimator = {
  position: {
    from: { x: 0, y: 0 },
    to: { x: 50, y: 0 },
    duration: 1000,
    easing: spring(),
  },
  opacity: {
    from: 1,
    to: 0,
    duration: 1000,
    easing: spring(),
  },
};

// Shape Animation
const shapeAnimator = {
  size: {
    from: { width: 100, height: 100 },
    to: { width: 200, height: 200 },
    duration: 1000,
    easing: spring(),
  },
  roundness: {
    from: 0,
    to: 100,
    duration: 1000,
    easing: spring(),
  },
};

// Background Animation
const backgroundAnimator = {
  scale: {
    from: 1,
    to: 0,
    duration: 1000,
    easing: spring(),
  },
  offset: {
    from: 0,
    to: 100,
    duration: 1000,
    easing: spring(),
  },
};

// Cursor Animation
const cursorAnimator = {
  position: {
    from: { x: 0, y: 0 },
    to: { x: 50, y: 50 },
    duration: 1000,
    easing: spring(),
  },
  scale: {
    from: 1,
    to: 2,
    duration: 1000,
    easing: spring(),
  },
};

export default function MyComponent() {
  return (
    <div>
      <TextAnimator animator={textAnimator} />
      <ShapeAnimator animator={shapeAnimator} />
      <BackgroundAnimator animator={backgroundAnimator} />
      <CursorAnimator animator={cursorAnimator} />
    </div>
  );
}
```

Note that this is a simplified version of the code and you may need to adjust it to fit your specific use case.

**Recipe:**

1. **Button Click Animation**
	* Set a keyframe for the button's scale at 0% (frame 0)
	* Set another keyframe for the button's scale at 100% (frame 10)
	* Copy the keyframe and paste it at frame 20
	* Set the easing to ease-in on the first keyframe and ease-out on the second keyframe
	* Set the easing to ease-in on the second keyframe and ease-out on the third keyframe
	* Use the Graph Editor to adjust the easing curve
2. **Button Darkening**
	* Add an Exposure effect to the button
	* Set a keyframe for the Exposure effect at 0% (frame 0)
	* Set another keyframe for the Exposure effect at 100% (frame 10)
	* Set the easing to ease-in on the first keyframe and ease-out on the second keyframe
	* Use the Graph Editor to adjust the easing curve
3. **Transition Animation**
	* Set a keyframe for the null's position at 0% (frame 0)
	* Set another keyframe for the null's position at 100% (frame 30)
	* Use the Graph Editor to adjust the easing curve
	* Add a 3D layer to the cursor and null
	* Move the cursor and null towards the camera
	* Scale down the cursor and null
4. **Scene Transition**
	* Select all layers excluding the background
	* Hold shift and hit Alt right bracket to cut the animation at the peak
	* Move the layers to the next scene

**Remotion Code:**

```jsx
import { spring } from 'remotion';

const buttonScale = spring(1, {
  mass: 1,
  damping: 100,
  stiffness: 100,
  overshootClamping: true,
});

const exposure = spring(1, {
  mass: 1,
  damping: 100,
  stiffness: 100,
  overshootClamping: true,
});

const nullPosition = spring(0, {
  mass: 1,
  damping: 100,
  stiffness: 100,
  overshootClamping: true,
});

const cursorScale = spring(1, {
  mass: 1,
  damping: 100,
  stiffness: 100,
  overshootClamping: true,
});

const cursorPosition = spring(0, {
  mass: 1,
  damping: 100,
  stiffness: 100,
  overshootClamping: true,
});

const textScale = spring(1, {
  mass: 1,
  damping: 100,
  stiffness: 100,
  overshootClamping: true,
});

const textPosition = spring(0, {
  mass: 1,
  damping: 100,
  stiffness: 100,
  overshootClamping: true,
});

const animation = () => {
  const currentTime = useCurrentFrame();

  const buttonScaleValue = buttonScale(currentTime);
  const exposureValue = exposure(currentTime);
  const nullPositionValue = nullPosition(currentTime);
  const cursorScaleValue = cursorScale(currentTime);
  const cursorPositionValue = cursorPosition(currentTime);
  const textScaleValue = textScale(currentTime);
  const textPositionValue = textPosition(currentTime);

  return (
    <div>
      <button
        style={{
          transform: `scale(${buttonScaleValue})`,
          filter: `brightness(${exposureValue})`,
        }}
      >
        Click me!
      </button>
      <div
        style={{
          position: 'absolute',
          left: `${nullPositionValue}px`,
          transform: `scale(${cursorScaleValue})`,
          transform: `translateX(${cursorPositionValue}px)`,
        }}
      >
        <div
          style={{
            transform: `scale(${textScaleValue})`,
            transform: `translateX(${textPositionValue}px)`,
          }}
        >
          Hello!
        </div>
      </div>
    </div>
  );
};
```

Note that this code uses the `spring` function from `remotion` to animate the values. The `spring` function takes an initial value and a set of parameters to control the animation. The `useCurrentFrame` hook is used to get the current frame number, which is used to animate the values.
