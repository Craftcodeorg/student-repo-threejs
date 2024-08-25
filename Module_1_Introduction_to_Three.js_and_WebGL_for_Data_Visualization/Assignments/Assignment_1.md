### Assignment: Interactive 3D Data Visualization with Three.js

---

#### Problem Statement

Create an interactive 3D bar chart using Three.js to visualize a dataset representing monthly sales figures for a fictional company. The chart should allow users to interact with the bars to display detailed sales information for each month. This task will help you apply key concepts from the lecture, such as scene creation, materials, and interactivity, in a practical scenario relevant to Data Engineering and Web Development.

---

#### Starter Code

Below is the starter code to set up a basic Three.js scene. You will need to build upon this framework to create the interactive 3D bar chart.

```javascript
// Starter code for setting up a Three.js scene

// Import Three.js library (ensure you have it installed in your project)
import * as THREE from 'three';

// Create a scene
const scene = new THREE.Scene();

// Set up a camera
const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
camera.position.z = 10;

// Set up a renderer and add it to the document
const renderer = new THREE.WebGLRenderer();
renderer.setSize(window.innerWidth, window.innerHeight);
document.body.appendChild(renderer.domElement);

// Create an array of sales data (in thousands)
const salesData = [12, 19, 3, 5, 2, 3, 10, 15, 7, 8, 12, 14];

// Function to create bars
function createBar(height, positionX) {
    const geometry = new THREE.BoxGeometry(0.5, height, 0.5);
    const material = new THREE.MeshBasicMaterial({ color: 0x0077ff });
    const bar = new THREE.Mesh(geometry, material);
    bar.position.x = positionX;
    bar.position.y = height / 2;
    scene.add(bar);
}

// Create bars based on sales data
salesData.forEach((value, index) => {
    createBar(value, index - salesData.length / 2);
});

// Animation loop
function animate() {
    requestAnimationFrame(animate);
    renderer.render(scene, camera);
}

animate();
```

---

#### Detailed Instructions

**Step 1: Enhance the Bar Creation**

- Modify the `createBar` function to include a label for each bar that displays the month name below it.
- Use `THREE.TextGeometry` or an equivalent method to create text labels.

**Step 2: Add Interactivity**

- Implement mouse hover functionality that highlights a bar when the user hovers over it.
- Display a tooltip showing the exact sales figure when a bar is clicked.

**Step 3: Improve Visual Aesthetics**

- Apply different colors to the bars based on sales performance (e.g., green for above average and red for below average).
- Add lighting effects to enhance the visual appearance of the chart.

**Step 4: Optimize for Performance**

- Ensure the scene renders smoothly by optimizing the geometry and materials used.
- Consider adding controls to allow users to rotate and zoom into the chart for better interaction.

---

#### Criteria for Success and Evaluation

**Success Criteria:**

- The bar chart accurately represents the sales data with interactive features.
- The code is well-structured, documented, and follows best practices.
- The application is visually appealing and performs smoothly.

**Evaluation Rubric:**

| Criteria               | Excellent (5) | Good (4) | Satisfactory (3) | Needs Improvement (2) | Unsatisfactory (1) |
|------------------------|---------------|----------|------------------|-----------------------|---------------------|
| Data Representation    | Accurate and detailed with interactivity | Accurate with basic interactivity | Mostly accurate | Partially accurate | Inaccurate |
| Code Quality           | Clean, well-documented, efficient | Mostly clean and documented | Adequate documentation | Some documentation | Poorly documented |
| Visual Appeal          | Highly aesthetic with lighting and colors | Aesthetic with some enhancements | Basic aesthetics | Minimal aesthetics | Unattractive |
| Performance            | Smooth rendering and interaction | Mostly smooth rendering | Occasional lag | Frequent lag | Poor performance |

This assignment aims to reinforce your understanding of Three.js and WebGL while helping you build practical skills in creating interactive data visualizations relevant to your career goals in Data Engineering and Web Development.