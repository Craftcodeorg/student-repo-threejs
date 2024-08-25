```markdown
### Exercise 2: Implement Dynamic Lighting in a Scene ###

#### Problem Statement:
As a Data Engineer and Full-Stack Developer, your goal is to enhance the realism of a 3D visualization of a global news dashboard using Three.js. This dashboard will feature a rotating globe with data points representing news hotspots. Your task is to implement dynamic lighting to highlight these hotspots effectively, ensuring the visualization is both informative and visually compelling.

Using the concepts from the lecture on lighting and shadows, you need to:

1. Add an **ambient light** to ensure basic visibility of the globe and data points.
2. Implement a **directional light** to simulate sunlight, casting realistic shadows on the globe.
3. Use a **spotlight** to focus on specific news hotspots as they rotate into view, enhancing user engagement.

#### Fill-in-the-Blank Starter Code:
```javascript
// Import Three.js library
import * as THREE from 'three';

// Create the scene
const scene = new THREE.Scene();

// Add ambient light for basic visibility
const ambientLight = new THREE.AmbientLight(0x404040); // soft white light
scene.add(ambientLight);

// Implement directional light to simulate sunlight
const directionalLight = new THREE.DirectionalLight(0xffffff, 1);
directionalLight.position.set(_____, _____, _____); // Fill in the position coordinates
directionalLight.castShadow = true;
scene.add(directionalLight);

// Add spotlight to highlight news hotspots
const spotLight = new THREE.SpotLight(0xffffff);
spotLight.position.set(_____, _____, _____); // Fill in the position coordinates
spotLight.angle = Math.PI / 6; // Spotlight angle
spotLight.penumbra = 0.1; // Soft edges
scene.add(spotLight);

// Render the scene (Assume renderer and camera are already set up)
function animate() {
    requestAnimationFrame(animate);
    // Rotate the globe here if needed
    renderer.render(scene, camera);
}
animate();
```

#### Hints:
1. **Directional Light Position**: Think about where the "sun" would be in relation to your globe. Typically, this would be above and slightly to the side.
2. **Spotlight Position**: Consider placing it at an angle that focuses on the equator or main areas of interest on your globe.
3. **Shadow Casting**: Ensure that objects like your globe are set to cast and receive shadows for realism.

#### Expected Outcome:
Upon completing this exercise, you should have a Three.js scene with dynamic lighting that enhances the visualization of your global news dashboard. The ambient light will ensure visibility, while the directional light provides depth with shadows. The spotlight will focus on rotating hotspots, drawing user attention to key areas. This setup will demonstrate your ability to apply lighting concepts to create engaging and realistic 3D visualizations in web applications.

Ensure your code includes error handling and comments explaining each step, adhering to best practices as discussed in the lecture.

---

### Integration ###
- This exercise is designed for intermediate-level developers with experience in JavaScript and Three.js.
- It is structured to be integrated into an interactive learning platform, using markdown for clear formatting.
- Additional resources: [Three.js Documentation](https://threejs.org/docs/), [Lighting Examples](https://threejs.org/examples/#webgl_lights_spotlight).
```
