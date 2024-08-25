### Assignment: Visualizing Real-Time Data with Three.js

---

#### Problem Statement:

In this assignment, you will apply your knowledge of setting up a Three.js environment to create an interactive 3D data visualization. The task is to visualize a set of data points representing real-time temperature readings from various cities around the world. You will create a 3D globe and plot these data points on it, using different colors to represent temperature ranges. This project simulates a real-world application relevant to Data Engineering and Web Development, where visualizing geographical data in an engaging manner is crucial.

---

#### Starter Code:

Below is the starter code that sets up a basic Three.js scene with a rotating globe. Your task will be to enhance this code by adding data points to the globe.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>3D Globe with Three.js</title>
    <style>
        body { margin: 0; }
        canvas { display: block; }
    </style>
</head>
<body>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
    <script>
        // Step 1: Set up the scene, camera, and renderer
        const scene = new THREE.Scene();
        const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
        const renderer = new THREE.WebGLRenderer();
        renderer.setSize(window.innerWidth, window.innerHeight);
        document.body.appendChild(renderer.domElement);

        // Step 2: Create a sphere to represent the globe
        const globeGeometry = new THREE.SphereGeometry(5, 32, 32);
        const globeMaterial = new THREE.MeshBasicMaterial({ color: 0x0000ff, wireframe: true });
        const globe = new THREE.Mesh(globeGeometry, globeMaterial);
        scene.add(globe);

        // Position the camera
        camera.position.z = 15;

        // Step 3: Animation loop
        function animate() {
            requestAnimationFrame(animate);
            globe.rotation.y += 0.001; // Rotate the globe
            renderer.render(scene, camera);
        }
        animate();

        // TODO: Step 4 - Add data points to the globe
        // Use the following data structure for temperature readings
        const temperatureData = [
            { city: "New York", lat: 40.7128, lon: -74.0060, temp: 22 },
            { city: "London", lat: 51.5074, lon: -0.1278, temp: 15 },
            { city: "Tokyo", lat: 35.6895, lon: 139.6917, temp: 30 },
            // Add more data points as needed
        ];

        // Function to convert latitude and longitude to 3D coordinates
        function convertLatLonToXYZ(lat, lon) {
            const radius = 5;
            const phi = (90 - lat) * (Math.PI / 180);
            const theta = (lon + 180) * (Math.PI / 180);

            return {
                x: -(radius * Math.sin(phi) * Math.cos(theta)),
                y: radius * Math.cos(phi),
                z: radius * Math.sin(phi) * Math.sin(theta)
            };
        }

        // TODO: Implement function to plot data points on the globe
    </script>
</body>
</html>
```

---

#### Detailed Instructions:

1. **Plotting Data Points**:
   - Implement a function to plot temperature data points on the globe.
   - Use the `convertLatLonToXYZ` function to determine the position of each point on the globe.
   - Represent each temperature reading as a small sphere with a color corresponding to its temperature range (e.g., blue for cold, red for hot).

2. **Enhancing Interactivity**:
   - Allow users to hover over or click on a data point to see detailed information about the city and its temperature.
   - Use `THREE.Raycaster` for detecting mouse interactions with the data points.

3. **Visual Feedback**:
   - Add visual feedback when a user interacts with a data point (e.g., change color or scale of the sphere).
   - Ensure that the globe remains interactive and visually appealing.

---

#### Criteria for Success and Evaluation:

- **Functionality**:
  - The globe should rotate smoothly, and data points should be plotted accurately based on latitude and longitude.
  - User interactions should display correct information about each city and its temperature.

- **Code Quality**:
  - The code should be clean, well-organized, and documented.
  - Follow best practices in JavaScript and Three.js coding.

- **User Experience**:
  - The visualization should be interactive and provide clear visual feedback.
  - Ensure that the application is responsive and works well across different devices.

By completing this assignment, you will gain practical experience in using Three.js for real-time data visualization, a valuable skill in Data Engineering and Web Development.