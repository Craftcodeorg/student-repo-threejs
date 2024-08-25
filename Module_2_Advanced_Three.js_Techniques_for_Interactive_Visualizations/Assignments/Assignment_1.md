### Assignment: Interactive Visualization with Custom Geometries and Materials in Three.js

---

#### Problem Statement:
Create a dynamic 3D visualization of a stock market dashboard using Three.js. Your task is to design and implement a set of interactive 3D shapes, each representing a different stock. Use advanced geometries such as extrusions and lathe geometries to model these shapes. Apply different materials to distinguish between stocks that have increased in value (bullish) and those that have decreased (bearish). This visualization should be capable of updating in real-time as new stock data is received.

---

#### Starter Code:
The following starter code sets up a basic Three.js scene. Your task is to build upon this framework by adding custom geometries and materials.

```javascript
// Import Three.js
import * as THREE from 'three';

// Create a scene
const scene = new THREE.Scene();

// Set up a camera
const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
camera.position.z = 5;

// Create a renderer
const renderer = new THREE.WebGLRenderer();
renderer.setSize(window.innerWidth, window.innerHeight);
document.body.appendChild(renderer.domElement);

// Function to create a stock representation
function createStockShape(stockData) {
    // TODO: Implement custom geometry and material based on stockData
    // Example: Use ExtrudeGeometry or LatheGeometry for complex shapes
    // Use MeshStandardMaterial for lighting effects

    // Placeholder geometry and material
    const geometry = new THREE.BoxGeometry();
    const material = new THREE.MeshStandardMaterial({ color: 0x0077ff });
    const mesh = new THREE.Mesh(geometry, material);

    return mesh;
}

// Sample stock data
const stocks = [
    { name: 'Stock A', value: 120, change: 5 },
    { name: 'Stock B', value: 95, change: -3 },
    // More stocks...
];

// Add stocks to the scene
stocks.forEach(stock => {
    const stockShape = createStockShape(stock);
    scene.add(stockShape);
});

// Animation loop
function animate() {
    requestAnimationFrame(animate);
    renderer.render(scene, camera);
}

animate();
```

---

#### Detailed Instructions:

1. **Step 1: Implement Custom Geometries**
   - Modify the `createStockShape` function to use `THREE.ExtrudeGeometry` or `THREE.LatheGeometry` for creating complex shapes.
   - Customize the geometry based on stock data (e.g., use extrusion depth to represent stock value).

2. **Step 2: Apply Materials**
   - Use `THREE.MeshStandardMaterial` to apply different colors or textures based on the stock's performance.
   - For bullish stocks (positive change), use a green color. For bearish stocks (negative change), use a red color.

3. **Step 3: Real-Time Data Integration**
   - Simulate real-time data updates by periodically changing the stock data and updating the scene.
   - Ensure that the visualization reflects these changes dynamically.

4. **Step 4: Enhance Interactivity**
   - Implement mouse interaction to display stock details when hovering over a shape.
   - Use `THREE.Raycaster` for detecting mouse events.

---

#### Criteria for Success and Evaluation:

- **Functionality**: The visualization correctly represents each stock with a unique 3D shape and updates in real-time.
- **Visual Appeal**: The use of advanced geometries and materials enhances the visual appeal and provides clear differentiation between bullish and bearish stocks.
- **Interactivity**: Users can interact with the visualization to get detailed information about each stock.
- **Code Quality**: The code is well-structured, commented, and follows best practices for readability and maintainability.

This assignment will help reinforce your understanding of advanced geometries and materials in Three.js, while also providing practical experience in creating interactive data visualizations relevant to Data Engineering and Web Development.