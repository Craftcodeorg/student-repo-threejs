### Assignment: Interactive Data Visualization with Custom Shaders

---

#### Problem Statement

In this assignment, you will create an interactive data visualization dashboard using Three.js that leverages custom shaders to represent real-time financial data. The goal is to build a dynamic bar chart where each bar's height and color dynamically change based on stock price fluctuations. This task will enhance your understanding of shaders in Three.js and their application in creating visually compelling data-driven web applications.

---

#### Starter Code

Below is the starter code to help you set up the environment. You will expand upon this by implementing custom shaders to achieve the desired visualization effects.

```javascript
// Basic Three.js setup
const scene = new THREE.Scene();
const camera = new THREE.PerspectiveCamera(75, window.innerWidth/window.innerHeight, 0.1, 1000);
const renderer = new THREE.WebGLRenderer();
renderer.setSize(window.innerWidth, window.innerHeight);
document.body.appendChild(renderer.domElement);

// Basic geometry and material setup
const geometry = new THREE.BoxGeometry(1, 1, 1);
const material = new THREE.MeshBasicMaterial({ color: 0x00ff00 });
const cube = new THREE.Mesh(geometry, material);
scene.add(cube);

camera.position.z = 5;

// Animation loop
function animate() {
    requestAnimationFrame(animate);
    renderer.render(scene, camera);
}
animate();

// Placeholder for shader materials
// TODO: Implement custom vertex and fragment shaders
```

---

#### Detailed Instructions

**Step 1: Implement Vertex Shader**

- Modify the starter code to include a custom vertex shader.
- The vertex shader should dynamically alter the height of each bar based on stock prices.
- Use a varying variable to pass data from the vertex shader to the fragment shader.

**Step 2: Implement Fragment Shader**

- Develop a custom fragment shader that changes the color of each bar.
- Colors should transition from green (positive change) to red (negative change) based on real-time data.
- Use GLSL to write the shader logic.

**Step 3: Integrate Real-Time Data**

- Simulate real-time stock data using random values or integrate with a real API if available.
- Update the vertex and fragment shaders in real-time as data changes.

**Step 4: Optimize Performance**

- Ensure that your shader code is optimized for performance.
- Use techniques such as minimizing uniform updates and optimizing shader calculations.

---

#### Criteria for Success and Evaluation

**Success Criteria:**

- The dashboard correctly visualizes stock data with dynamic height and color changes.
- The shaders are efficiently integrated, with smooth animations and transitions.
- The code is well-documented, clean, and follows best practices.
- The application performs well without significant lag or stutter.

**Evaluation Rubric:**

| Criteria                  | Excellent (5) | Good (4) | Satisfactory (3) | Needs Improvement (2) | Unsatisfactory (1) |
|---------------------------|---------------|----------|------------------|-----------------------|--------------------|
| Shader Implementation     | Correctly uses vertex and fragment shaders with dynamic effects. | Uses shaders with minor issues. | Basic shader usage without dynamic effects. | Attempted shader usage with errors. | No shader implementation. |
| Real-Time Data Integration| Seamlessly integrates real-time data updates. | Integrates data with minor delays. | Basic data integration without real-time updates. | Attempted integration with significant issues. | No data integration. |
| Code Quality              | Clean, well-documented, follows best practices. | Mostly clean and documented. | Understandable but lacks documentation. | Poorly organized code. | Unreadable or non-functional code. |
| Performance Optimization  | Highly optimized with smooth performance. | Mostly optimized with minor issues. | Basic optimization with noticeable lag. | Poorly optimized with significant lag. | No optimization attempted. |

---

This assignment provides a practical scenario for applying your knowledge of Three.js shaders in a real-world context relevant to Data Engineering and Web Development, reinforcing your skills in building interactive and dynamic visualizations.