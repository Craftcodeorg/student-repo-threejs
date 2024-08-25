### Assignment: Real-Time News Visualization Platform

#### Problem Statement
Create a real-time news visualization platform that integrates multiple data sources using RESTful APIs and WebSockets. This platform should display a globe where users can see news articles pop up in real-time based on geolocation. The task involves using RESTful APIs to fetch historical news data and WebSockets to receive live news updates.

#### Starter Code
Below is the starter code to set up your environment. You will build upon this framework to complete the assignment.

```javascript
// Starter code for real-time news visualization

// Step 1: Set up the environment for a 3D globe using Three.js
const scene = new THREE.Scene();
const camera = new THREE.PerspectiveCamera(75, window.innerWidth/window.innerHeight, 0.1, 1000);
const renderer = new THREE.WebGLRenderer();
renderer.setSize(window.innerWidth, window.innerHeight);
document.body.appendChild(renderer.domElement);

// Step 2: Create a sphere to represent the Earth
const geometry = new THREE.SphereGeometry(5, 32, 32);
const material = new THREE.MeshBasicMaterial({ color: 0x00ff00 });
const earth = new THREE.Mesh(geometry, material);
scene.add(earth);

camera.position.z = 10;

// Step 3: Function to fetch historical news data using RESTful API
async function fetchHistoricalNews() {
    const response = await fetch('https://example-news-api.com/historical');
    const data = await response.json();
    // Process and visualize the data on the globe
}

// Step 4: Set up WebSocket connection for live news updates
const socket = new WebSocket('wss://example-news-api.com/live');
socket.onmessage = function(event) {
    const liveNewsData = JSON.parse(event.data);
    // Update the globe with real-time news data
};

// Render loop
function animate() {
    requestAnimationFrame(animate);
    earth.rotation.y += 0.01;
    renderer.render(scene, camera);
}
animate();
```

#### Detailed Instructions

**Step 1: Enhance the Globe Visualization**
- Modify the material of the globe to use a texture map of Earth.
- Add lighting to make the visualization more realistic.

**Step 2: Implement Historical News Data Visualization**
- Complete the `fetchHistoricalNews` function to plot historical news articles on the globe.
- Use markers or pins to represent news locations.

**Step 3: Real-Time News Integration**
- In the WebSocket message handler, update the globe with live news data.
- Ensure that new articles are dynamically added as they are received.

**Step 4: User Interaction**
- Allow users to click on markers to view headlines and summaries of news articles.
- Implement a search feature to filter news by keywords or regions.

#### Criteria for Success and Evaluation

**Success Criteria:**
- The globe accurately displays both historical and live news articles.
- The platform uses RESTful APIs and WebSockets effectively to handle data retrieval.
- The visualization is interactive, allowing users to explore news articles.
- The code is clean, well-documented, and follows JavaScript best practices.

**Evaluation Rubric:**
- **Functionality (40%)**: The platform meets all functional requirements and handles real-time data effectively.
- **Code Quality (30%)**: The code is well-organized, commented, and adheres to best practices.
- **User Experience (20%)**: The visualization is intuitive and engaging for users.
- **Innovation (10%)**: Creative use of visualization techniques and additional features beyond the basic requirements.

This assignment simulates a real-world scenario where you apply your skills in data integration and visualization, reinforcing your learning from the lecture.