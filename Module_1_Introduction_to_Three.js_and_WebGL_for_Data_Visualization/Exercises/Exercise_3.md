### Module Title: Introduction to Three.js and WebGL for Data Visualization ###

---

### Exercise 3: Implement Camera Controls for Scene Navigation ###

#### 1. **Problem Statement**

You are tasked with enhancing a basic Three.js application by implementing camera controls that allow users to navigate a 3D visualization of real-time world news data. Using the concepts from the lecture on Scene, Camera, and Renderer, your goal is to create an interactive experience where users can explore the data by rotating, zooming, and panning the camera. This will simulate an immersive environment akin to navigating a globe with news hotspots.

**Scenario**: Imagine you are developing a web-based globe that visualizes current world news. Users should be able to interact with this globe to view different regions and the associated news data. Implement camera controls using `OrbitControls` from the Three.js library to achieve this functionality.

---

#### 2. **Fill-in-the-Blank Starter Code**

```javascript
// Import necessary components from Three.js
import * as THREE from 'three';
import { OrbitControls } from 'three/examples/jsm/controls/OrbitControls.js';

// Basic setup for a Three.js application
const scene = new THREE.Scene();
const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
const renderer = new THREE.WebGLRenderer();

renderer.setSize(window.innerWidth, window.innerHeight);
document.body.appendChild(renderer.domElement);

// Add a sphere to represent the globe
const geometry = new THREE.SphereGeometry(5, 32, 32);
const material = new THREE.MeshBasicMaterial({ color: 0x0077ff, wireframe: true });
const globe = new THREE.Mesh(geometry, material);
scene.add(globe);

// Position the camera
camera.position.z = 10;

// Implement OrbitControls for camera navigation
const controls = new OrbitControls(camera, renderer.domElement);
controls.enableDamping = true; // Enable damping for smoother controls
controls.dampingFactor = 0.25; // Set the damping factor
controls.enableZoom = true; // Allow zooming

function animate() {
  requestAnimationFrame(animate);
  
  // Update controls in each frame
  controls.update();
  
  renderer.render(scene, camera);
}

animate();
```

---

#### 3. **Hints**

- **Hint 1**: Consider how `OrbitControls` can be used to facilitate user interaction with the scene. Review its properties such as `enableZoom`, `enableRotate`, and `enablePan` to enhance user experience.
- **Hint 2**: Remember to call `controls.update()` within your animation loop to ensure that any changes to the controls are reflected in real-time.
- **Hint 3**: Experiment with different `dampingFactor` values to achieve the desired smoothness in camera movements.

---

#### 4. **Expected Outcome**

Upon completing this exercise, you should have a functional Three.js application where users can interactively navigate a 3D globe representing world news data. The camera should smoothly transition as users rotate, zoom, and pan around the globe. The final solution should demonstrate a clear understanding of Three.js camera controls and their application in creating interactive data visualizations.

**Key Features**:
- Interactive navigation using `OrbitControls`.
- Smooth camera transitions with appropriate damping.
- A well-commented codebase explaining each component's role and functionality.

---

### Integration ###

This exercise is designed to integrate seamlessly into your learning platform. Ensure you provide links to necessary resources such as the Three.js library and any additional documentation on `OrbitControls`. Use markdown formatting for clarity and structure, facilitating easy navigation through sections and code snippets.