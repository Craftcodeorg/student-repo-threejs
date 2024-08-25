### Module Title: Advanced Three.js Techniques for Interactive Visualizations ###

---

### Exercise 3: Optimize a Three.js Scene for Performance ###

#### 1. Problem Statement:

You have been tasked with optimizing a Three.js scene that visualizes real-time financial data using custom shaders. The current implementation uses a vertex shader to animate stock price bars and a fragment shader to change their color based on performance. However, the scene is not performing efficiently, especially when visualizing a large dataset. Your goal is to apply optimization techniques to enhance the performance of this scene while maintaining its interactive and dynamic nature.

**Scenario:**
- You are developing a stock market dashboard that displays real-time data for hundreds of stocks. Each stock is represented by a bar whose height and color change dynamically.
- The current implementation suffers from performance issues such as lag and high memory usage.

**Tasks:**
1. Identify and implement at least three optimization techniques to improve the performance of the Three.js scene.
2. Ensure that the shaders remain effective in visualizing real-time data changes.
3. Document the changes and their impact on performance.

---

#### 2. Fill-in-the-Blank Starter Code:

```javascript
// Starter code for optimizing a Three.js scene with shaders

// Vertex Shader
const vertexShader = `
  varying float height;
  void main() {
    height = position.y;
    gl_Position = projectionMatrix * modelViewMatrix * vec4(position, 1.0);
  }
`;

// Fragment Shader
const fragmentShader = `
  varying float height;
  void main() {
    gl_FragColor = vec4(height / 10.0, 0.0, 1.0 - height / 10.0, 1.0);
  }
`;

// Create Shader Material
const customMaterial = new THREE.ShaderMaterial({
  vertexShader,
  fragmentShader
});

// Optimization: Use InstancedMesh for efficient rendering
const geometry = new THREE.BoxGeometry(1, 1, 1);
const material = new THREE.MeshBasicMaterial({color: 0xffffff});
const instancedMesh = new THREE.InstancedMesh(geometry, material, _______); // Fill in the number of instances

// Function to update instance matrices
function updateInstances(data) {
  for (let i = 0; i < data.length; i++) {
    const matrix = new THREE.Matrix4();
    matrix.setPosition(_______, data[i].price, _______); // Fill in position based on data
    instancedMesh.setMatrixAt(i, matrix);
  }
  instancedMesh.instanceMatrix.needsUpdate = true;
}

// Render loop
function animate() {
  requestAnimationFrame(animate);
  // Add optimization logic here
  renderer.render(scene, camera);
}

animate();
```

---

#### 3. Hints:

- **Hint 1:** Consider using `InstancedMesh` to reduce the number of draw calls when rendering multiple identical objects with different transformations.
- **Hint 2:** Use `Frustum Culling` to avoid rendering objects that are outside the camera's view.
- **Hint 3:** Optimize shaders by reducing calculations inside the shader code and pre-computing values where possible.

---

#### 4. Expected Outcome:

Upon completing this exercise, you should be able to optimize a Three.js scene effectively by applying techniques such as instancing, culling, and shader optimization. Your final solution should demonstrate improved performance metrics such as frame rate and memory usage without compromising the visual integrity of the data visualization. The code should be well-documented, with comments explaining each optimization step and its impact.

---

### Integration ###

- Ensure that your solution is modular and can be easily integrated into existing projects.
- Use markdown formatting for clear presentation and include any additional resources or documentation links that may assist in understanding the optimization techniques applied.
- Submit your optimized code along with a brief report on performance improvements observed before and after optimization.

---