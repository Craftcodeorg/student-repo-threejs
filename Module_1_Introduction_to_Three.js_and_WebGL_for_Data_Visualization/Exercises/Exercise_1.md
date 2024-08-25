## Module Title: Introduction to Three.js and WebGL for Data Visualization

### Exercise 1: Set up a Three.js Project with a Basic Scene

---

#### Problem Statement

As a Data Engineer and aspiring Full-Stack Developer, your goal is to create a foundational setup for a Three.js project that will eventually visualize real-time world news on a web-based globe. This exercise will guide you through setting up a basic Three.js scene, which will serve as the starting point for more complex visualizations.

**Scenario:** You are tasked with building the initial framework for a 3D globe visualization tool. The first step is to create a simple Three.js scene with a rotating cube, simulating the Earth. This setup will help you understand the basics of Three.js and WebGL, which are crucial for rendering interactive data visualizations.

---

#### Fill-in-the-Blank Starter Code

Below is the starter code for setting up a basic Three.js scene. Fill in the blanks to complete the functionality.

```javascript
// Import the necessary Three.js components
import * as THREE from 'three';

// Create a scene
var scene = new THREE.Scene();

// Set up a camera with perspective view
var camera = new THREE.PerspectiveCamera(75, window.innerWidth/window.innerHeight, 0.1, 1000);

// Initialize the WebGL renderer
var renderer = new THREE.WebGLRenderer();
renderer.setSize(window.innerWidth, window.innerHeight);
document.body.appendChild(renderer.domElement);

// Define geometry and material for the cube
var geometry = new THREE.BoxGeometry();
var material = new THREE.MeshBasicMaterial({color: 0x00ff00});

// Create a mesh by combining geometry and material
var cube = new THREE.Mesh(geometry, material);

// Add the cube to the scene
scene.add(cube);

// Position the camera
camera.position.z = 5;

// Animation loop to render the scene
var animate = function () {
    requestAnimationFrame(animate);
    
    // Rotate the cube on its x and y axes
    cube.rotation.x += 0.01;
    cube.rotation.y += 0.01;
    
    // Render the scene from the perspective of the camera
    renderer.render(scene, camera);
};

// Call the animate function to start the loop
animate();
```

**Blanks to Fill:**
1. `import * as THREE from '______';` - Import statement for Three.js.
2. `camera = new THREE.PerspectiveCamera(_____, window.innerWidth/window.innerHeight, 0.1, 1000);` - Set the field of view for the camera.
3. `cube.rotation.x += ____;` - Increment value for cube rotation on the x-axis.
4. `cube.rotation.y += ____;` - Increment value for cube rotation on the y-axis.

---

#### Hints

1. **Three.js Import**: Ensure you have installed Three.js in your project. The import statement should reference the Three.js library.
2. **Camera Field of View**: The field of view is typically set between 45 and 75 degrees for perspective cameras in Three.js.
3. **Cube Rotation**: The rotation increments should be small values to create smooth animation; consider using values around 0.01.
4. **Rendering Loop**: Remember that `requestAnimationFrame` is used to create smooth animations by calling the animate function repeatedly.

---

#### Expected Outcome

Upon completing this exercise, you should have a working Three.js project with a basic scene featuring a rotating cube. This exercise demonstrates your understanding of setting up a Three.js environment and manipulating basic objects within it. The final solution should be well-commented, explaining each step clearly, and include error handling where necessary, adhering to best practices in web development.

---

### Integration

- **File Structure**: Ensure your project includes an `index.html` file to host your JavaScript code and any necessary dependencies.
- **Resources**: [Three.js Documentation](https://threejs.org/docs/) for further reading and understanding of concepts.
- **Community Collaboration**: Consider sharing your progress in web development forums or groups to receive feedback and tips from experienced developers.

This exercise aligns with your career goals by providing hands-on experience with Three.js and setting the foundation for more complex data visualizations in future modules.