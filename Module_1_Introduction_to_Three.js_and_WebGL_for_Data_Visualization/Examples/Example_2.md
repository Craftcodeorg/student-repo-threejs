# Module Title: Introduction to Three.js and WebGL for Data Visualization

## Example 2: Creating a Rotating Cube

### 1. Introduction

In the realm of Data Engineering and Web Development, the ability to visualize data in an interactive and engaging manner is crucial. "Example 2: Creating a Rotating Cube" serves as a foundational exercise in understanding how to set up a Three.js environment, which is pivotal for creating 3D visualizations on the web. This example builds upon the key concepts discussed in the lecture, such as setting up a scene, camera, and renderer, to create dynamic visual content that can be used to represent complex data sets. For a Data Engineer and Full-Stack Developer, mastering these skills is essential for integrating real-time data into interactive dashboards and applications, thereby enhancing user experience and providing actionable insights.

### 2. Code Snippet

Below is a well-commented code snippet illustrating the concept of creating a rotating cube using Three.js. This code is designed for an intermediate-level programmer and includes best practices and error handling.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rotating Cube with Three.js</title>
    <!-- Include Three.js library -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
</head>
<body>
    <script>
        // Initialize scene, camera, and renderer
        const scene = new THREE.Scene();
        const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
        const renderer = new THREE.WebGLRenderer();
        renderer.setSize(window.innerWidth, window.innerHeight);
        document.body.appendChild(renderer.domElement);

        // Create a cube geometry and material
        const geometry = new THREE.BoxGeometry();
        const material = new THREE.MeshBasicMaterial({ color: 0x00ff00 });
        const cube = new THREE.Mesh(geometry, material);
        scene.add(cube);

        // Set camera position
        camera.position.z = 5;

        // Animation loop
        function animate() {
            requestAnimationFrame(animate);
            // Rotate the cube
            cube.rotation.x += 0.01;
            cube.rotation.y += 0.01;
            // Render the scene from the perspective of the camera
            renderer.render(scene, camera);
        }

        // Error handling for window resize
        window.addEventListener('resize', () => {
            const width = window.innerWidth;
            const height = window.innerHeight;
            renderer.setSize(width, height);
            camera.aspect = width / height;
            camera.updateProjectionMatrix();
        });

        // Start animation
        animate();
    </script>
</body>
</html>
```

### 3. Explanation

This code snippet demonstrates the creation of a simple rotating cube using Three.js:

- **Scene Setup**: The `THREE.Scene()` creates a container to hold objects, lights, and cameras.
- **Camera Configuration**: A `THREE.PerspectiveCamera` is set up to simulate human eye perspective, with parameters defining field of view, aspect ratio, and near/far clipping planes.
- **Renderer Initialization**: `THREE.WebGLRenderer` is used to render the scene onto the HTML document. It is configured to match the browser window size.
- **Cube Creation**: A cube is created using `THREE.BoxGeometry` for its shape and `THREE.MeshBasicMaterial` for its appearance. The cube is added to the scene.
- **Animation Loop**: The `animate` function uses `requestAnimationFrame` to continuously render frames. The cube's rotation properties are updated in each frame to achieve a spinning effect.
- **Responsive Design**: An event listener adjusts the renderer size and camera aspect ratio on window resize to maintain visual consistency.

This setup allows developers to create dynamic and interactive 3D visualizations, which are crucial in data-driven applications.

### 4. Application

In Data Engineering and Web Development, creating a rotating cube with Three.js can serve as a stepping stone for more complex visualizations:

- **Data Dashboards**: Use rotating cubes or other shapes to represent data metrics dynamically on dashboards. For instance, a cube's color or rotation speed could change based on real-time data inputs.
- **Interactive Reports**: Enhance reports with interactive 3D elements that users can manipulate to explore data from different angles.
- **Educational Tools**: Develop educational platforms where users can interact with 3D models to better understand spatial relationships in data.

By mastering these fundamental skills in Three.js, you can significantly improve how data is presented and interacted with on web platforms, aligning with your career goals of creating innovative data-driven applications.