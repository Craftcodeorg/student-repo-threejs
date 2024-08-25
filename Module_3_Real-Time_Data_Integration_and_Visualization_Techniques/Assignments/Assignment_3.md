### Assignment: Real-Time Sports Data Visualization with Three.js ###

#### Problem Statement ####
You are tasked with creating a real-time sports data visualization dashboard using Three.js. Your goal is to visualize live football (soccer) match statistics, such as player positions and ball movement, on a 3D field. This will involve integrating real-time data from a sports API, updating the visualization dynamically, and allowing user interaction to explore different aspects of the match. This assignment will help you apply the concepts of real-time data integration and 3D visualization, which are crucial in Data Engineering and Web Development.

#### Starter Code ####
Below is the starter code to set up a basic Three.js environment. You will build upon this framework to create your interactive sports data visualization.

```javascript
// Starter code for Three.js setup

// Import Three.js library
import * as THREE from 'three';

// Set up the scene, camera, and renderer
const scene = new THREE.Scene();
const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
const renderer = new THREE.WebGLRenderer();
renderer.setSize(window.innerWidth, window.innerHeight);
document.body.appendChild(renderer.domElement);

// Create a basic plane to represent the football field
const geometry = new THREE.PlaneGeometry(100, 50);
const material = new THREE.MeshBasicMaterial({ color: 0x00ff00 });
const field = new THREE.Mesh(geometry, material);
scene.add(field);

// Position the camera
camera.position.z = 100;

// Function to update scene with real-time data (to be implemented)
function updateScene(data) {
    // Logic to update player positions and ball movement
}

// Render loop
function animate() {
    requestAnimationFrame(animate);
    renderer.render(scene, camera);
}
animate();

// Placeholder function for fetching real-time sports data (to be implemented)
function fetchLiveData() {
    // Use WebSockets or API calls to get live data
}

// Call fetchLiveData at regular intervals
setInterval(fetchLiveData, 1000);
```

#### Detailed Instructions ####

**Step 1: Data Integration**
- Implement the `fetchLiveData` function to connect to a live sports API or WebSocket that provides real-time match data.
- Parse the received data to extract player positions and ball coordinates.

**Step 2: Updating Visuals**
- Modify the `updateScene` function to dynamically update the positions of players and the ball on the 3D field based on the real-time data.
- Use Three.js objects like `THREE.SphereGeometry` for players and `THREE.SphereGeometry` for the ball.

**Step 3: Enhancing Interactivity**
- Add controls using `THREE.OrbitControls` to allow users to rotate and zoom the view of the field.
- Implement click events to display additional information about players when they are clicked.

**Step 4: Performance Optimization**
- Ensure smooth performance by optimizing rendering and updating only when necessary.
- Consider using techniques like requestAnimationFrame throttling or object pooling.

#### Criteria for Success and Evaluation ####

**Success Criteria:**
- The dashboard accurately reflects real-time player positions and ball movements.
- The visualization is interactive, allowing users to explore different aspects of the match.
- The code is clean, well-documented, and follows best practices for readability and maintainability.
- The application performs efficiently without lag during updates.

**Evaluation Rubric:**
- **Accuracy (30%)**: Correct implementation of real-time data integration and visualization updates.
- **Interactivity (25%)**: Quality and usability of user interactions implemented.
- **Code Quality (25%)**: Cleanliness, documentation, and adherence to coding standards.
- **Performance (20%)**: Efficiency in rendering and updating visualizations without noticeable lag.

This assignment will reinforce your understanding of integrating real-time data into web applications using Three.js and help you develop skills applicable in Data Engineering and Web Development.