## Assignment 3: Develop a Basic Three.js Application with User Interaction

### Problem Statement

In this assignment, you will create an interactive 3D data visualization using Three.js. The task is to simulate a basic 3D bar chart that represents fictional stock prices over a week. Users should be able to interact with the chart by rotating the view to explore different perspectives. This assignment will reinforce your understanding of the Scene, Camera, and Renderer in Three.js and how they work together to create engaging data visualizations.

### Starter Code

Below is the starter code to set up your Three.js environment. You will build upon this framework by adding interactivity and enhancing the visualization.

```javascript
// Starter code for a basic Three.js application

// Step 1: Set up the scene, camera, and renderer
const scene = new THREE.Scene();
const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
const renderer = new THREE.WebGLRenderer();

renderer.setSize(window.innerWidth, window.innerHeight);
document.body.appendChild(renderer.domElement);

// Step 2: Create a simple bar geometry for the stock prices
const geometry = new THREE.BoxGeometry(1, 1, 1);
const material = new THREE.MeshBasicMaterial({ color: 0x00ff00 });
const bar = new THREE.Mesh(geometry, material);
scene.add(bar);

camera.position.z = 5;

// Step 3: Animate the scene
function animate() {
    requestAnimationFrame(animate);
    renderer.render(scene, camera);
}

animate();

// TODO: Implement user interaction to rotate the camera around the scene
```

### Detailed Instructions

1. **Enhance the Visualization**:
   - Modify the `geometry` to create multiple bars representing stock prices for each day of the week. Each bar should have a different height corresponding to its value.
   - Use an array to store the stock prices and iterate over this array to create and position each bar in the scene.

2. **Add User Interaction**:
   - Implement mouse or keyboard controls to allow users to rotate the camera around the bar chart. This will provide a more immersive experience as users can view the chart from different angles.
   - Consider using libraries like `THREE.OrbitControls` to simplify the implementation of user interactions.

3. **Improve Aesthetics**:
   - Experiment with different materials and colors for the bars to make the visualization more appealing.
   - Add lighting to the scene to enhance depth perception and realism.

4. **Optimize Performance**:
   - Ensure that the application runs smoothly by optimizing the rendering process and managing resources efficiently.

### Criteria for Success and Evaluation

- **Correct Implementation**:
  - The application correctly displays a 3D bar chart with bars representing stock prices.
  - User interaction is implemented effectively, allowing users to rotate and explore the visualization.

- **Code Quality**:
  - The code is clean, well-organized, and follows best practices in JavaScript and Three.js development.
  - Adequate comments are provided to explain the logic and functionality of different code sections.

- **User Experience**:
  - The visualization is aesthetically pleasing and easy to navigate.
  - The application performs well without noticeable lag or performance issues.

- **Innovation**:
  - Additional features or enhancements that go beyond the basic requirements are encouraged and will be considered in the evaluation.

This assignment aims to provide a practical coding task that reflects real-world applications in Data Engineering and Web Development, reinforcing your understanding of Three.js basics while allowing you to apply these concepts creatively.