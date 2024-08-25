### Assignment 2: Advanced Lighting and Shadows in Three.js

#### Problem Statement:
As a Data Engineer and Full-Stack Developer, you are tasked with enhancing a web-based financial application that visualizes stock market trends. Your goal is to create a realistic 3D scene using Three.js, incorporating advanced lighting techniques to improve the visual appeal and user experience. Specifically, you need to implement ambient and directional lighting to highlight key data points and create depth through shadows.

Your task is to build a 3D bar chart that represents stock prices over time. Use ambient light to ensure visibility across the scene and directional light to cast realistic shadows on the bars, enhancing the depth perception of the visualization.

#### Starter Code:
Below is the basic setup for your Three.js scene. You will expand this code by adding advanced lighting techniques as described in the instructions.

```javascript
// Starter code for creating a 3D bar chart with lighting

// Import Three.js library
import * as THREE from 'three';

// Create a scene
const scene = new THREE.Scene();

// Create a camera
const camera = new THREE.PerspectiveCamera(75, window.innerWidth/window.innerHeight, 0.1, 1000);
camera.position.z = 5;

// Create a renderer
const renderer = new THREE.WebGLRenderer();
renderer.setSize(window.innerWidth, window.innerHeight);
document.body.appendChild(renderer.domElement);

// Add ambient light
const ambientLight = new THREE.AmbientLight(0x404040); // soft white light
scene.add(ambientLight);

// Add directional light (students will modify this)
const directionalLight = new THREE.DirectionalLight(0xffffff, 1);
directionalLight.position.set(5, 10, 7.5);
directionalLight.castShadow = true;
scene.add(directionalLight);

// Create a bar (students will add more bars)
const geometry = new THREE.BoxGeometry(0.5, 1, 0.5);
const material = new THREE.MeshStandardMaterial({ color: 0x00ff00 });
const bar = new THREE.Mesh(geometry, material);
scene.add(bar);

// Render loop
function animate() {
    requestAnimationFrame(animate);
    renderer.render(scene, camera);
}
animate();
```

#### Detailed Instructions:

**Step 1: Implement Ambient Lighting**
- Ensure the ambient light is set up correctly to provide basic visibility across the entire scene. Adjust its intensity if necessary to ensure all elements are visible without overpowering other light sources.

**Step 2: Enhance Directional Lighting**
- Modify the directional light to mimic sunlight, casting realistic shadows on the bars. Adjust its position and intensity to create distinct shadows that enhance depth perception.
- Enable shadow casting for all bars in the scene by setting `castShadow` to `true` on each mesh.

**Step 3: Add Multiple Bars**
- Expand the scene by creating multiple bars of varying heights to represent different stock prices. Position them appropriately along the x-axis.
- Ensure each bar has a unique color or texture to differentiate between data points.

**Step 4: Optimize Performance**
- Adjust shadow map size and shadow bias settings to optimize performance without sacrificing visual quality. Consider the balance between shadow resolution and rendering speed.

**Criteria for Success and Evaluation:**

- **Lighting Implementation**: The scene must effectively use both ambient and directional lighting to enhance visibility and create realistic shadows.
- **Scene Composition**: Multiple bars should be correctly positioned and varied in height, representing different stock prices.
- **Performance Optimization**: The application should run smoothly with optimized shadow settings.
- **Code Quality**: The code should be clean, well-documented, and follow best practices in JavaScript and Three.js development.
- **User Experience**: The final visualization should be visually appealing and informative, providing users with an intuitive understanding of stock trends.

This assignment will help you apply advanced Three.js techniques in a practical scenario relevant to data visualization and web development, reinforcing your understanding of lighting and shadows in creating immersive applications.