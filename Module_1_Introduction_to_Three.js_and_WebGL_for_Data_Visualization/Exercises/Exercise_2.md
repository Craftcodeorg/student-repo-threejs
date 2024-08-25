### Module Title: Introduction to Three.js and WebGL for Data Visualization ###

---

### Exercise 2: Create and Animate a Simple 3D Object ###

#### Problem Statement:

In this exercise, you will apply the concepts learned in the lecture "Setting up a Three.js Environment" to create and animate a simple 3D object. Your task is to build a basic 3D scene that visualizes real-time data, such as stock market trends or geospatial data, using a rotating 3D bar chart. This exercise will help you understand how to integrate real-time data into your Three.js visualizations, aligning with your career goals in Data Engineering and Full-Stack Development.

---

#### Fill-in-the-Blank Starter Code:

Below is the starter code for setting up your Three.js environment and creating a rotating 3D bar chart. Fill in the blanks to complete the functionality.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Three.js Data Visualization</title>
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

        // Define geometry and material for the bar chart
        const geometry = new THREE.BoxGeometry(1, ________, 1); // Height represents data value
        const material = new THREE.MeshBasicMaterial({color: ________}); // Choose a color based on data category
        const bar = new THREE.Mesh(geometry, material);
        scene.add(bar);

        // Position camera
        camera.position.z = ________; // Adjust to fit the entire scene

        // Animation function
        function animate() {
            requestAnimationFrame(animate);
            bar.rotation.x += ________; // Adjust rotation speed
            bar.rotation.y += ________;
            renderer.render(scene, camera);
        }
        animate();
    </script>
</body>
</html>
```

---

#### Hints:

1. **Geometry Height**: Think about how the height of the bar can represent a data value, such as stock price or geographical elevation.
2. **Material Color**: Use different colors to distinguish between categories or ranges of data values. Consider using a color that aligns with the type of data being visualized.
3. **Camera Position**: Ensure the camera is positioned far enough back to view the entire object comfortably.
4. **Rotation Speed**: Experiment with different values to achieve a smooth rotation effect.

---

#### Expected Outcome:

Upon completing this exercise, you should have a functional 3D bar chart that rotates continuously in the scene. This visualization should demonstrate your ability to set up a Three.js environment and animate objects based on real-time data inputs. The final solution should include well-commented code that explains each step of the process, adhering to best practices in Data Engineering and Web Development.

---

### Integration ###

This exercise is designed to be seamlessly integrated into your learning platform. It uses markdown for formatting and includes all necessary resources within the HTML starter code. Ensure you review and test your code to verify its functionality before proceeding to more advanced topics in Three.js and data visualization.