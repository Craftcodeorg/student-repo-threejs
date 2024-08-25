### Assignment: Real-Time Data Integration and Visualization Techniques

---

#### Problem Statement:

Create a real-time stock market dashboard using Three.js and WebSockets. This application will visualize live stock data on a 3D globe, allowing users to see the current stock prices for various companies as they update in real-time. The goal is to integrate real-time data streams into a web application, demonstrating the concepts of data integration and visualization.

#### Starter Code:

Below is the starter code to help you set up the environment for the real-time stock market dashboard. The code initializes a basic Three.js scene and connects to a WebSocket server that streams stock data.

```javascript
// Starter code for a real-time stock market dashboard using Three.js

// Import necessary libraries
import * as THREE from 'three';
import io from 'socket.io-client';

// Initialize Three.js scene
const scene = new THREE.Scene();
const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
const renderer = new THREE.WebGLRenderer();
renderer.setSize(window.innerWidth, window.innerHeight);
document.body.appendChild(renderer.domElement);

// Create a basic sphere to represent the globe
const geometry = new THREE.SphereGeometry(5, 32, 32);
const material = new THREE.MeshBasicMaterial({ color: 0x0077ff, wireframe: true });
const globe = new THREE.Mesh(geometry, material);
scene.add(globe);

// Position the camera
camera.position.z = 10;

// Connect to WebSocket server for real-time stock data
const socket = io('https://yourserver.com');
socket.on('stockUpdate', (data) => {
    // TODO: Update globe with real-time stock data
    console.log('Stock Update:', data);
});

// Render loop
function animate() {
    requestAnimationFrame(animate);
    renderer.render(scene, camera);
}
animate();
```

#### Detailed Instructions:

1. **WebSocket Integration**:
   - Modify the WebSocket event listener to parse incoming stock data.
   - Extract relevant information such as company name, stock price, and location.

2. **Data Visualization on the Globe**:
   - Use Three.js to create markers or points on the globe representing different companies.
   - Each marker should reflect the current stock price using color or size variations.
   - Implement logic to update these markers in real-time as new data arrives.

3. **User Interaction**:
   - Enable users to interact with the globe (e.g., rotate, zoom).
   - Add tooltips or labels that display detailed information when hovering over a marker.

4. **Enhancements**:
   - Implement additional features such as filtering by sector or region.
   - Consider adding animations or transitions for visual appeal when data updates.

#### Criteria for Success and Evaluation:

- **Functionality**: The application should successfully connect to a WebSocket server and visualize real-time stock data on a 3D globe.
- **Real-Time Updates**: Stock data should update dynamically without page refreshes.
- **Interactivity**: Users should be able to interact with the globe and access detailed information about each company.
- **Code Quality**: The code should be clean, well-documented, and adhere to best practices.
- **User Experience**: The interface should be intuitive and visually engaging.

By completing this assignment, you will gain practical experience in integrating real-time data into web applications and visualizing it using Three.js, reinforcing your skills in Data Engineering and Web Development.