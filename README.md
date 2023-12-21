<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>3D Scene with Two Models</title>
    <script src="https://threejs.org/build/three.js"></script>
</head>
<body>
    <script>
        var scene = new THREE.Scene();
        var camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
        var renderer = new THREE.WebGLRenderer();
        renderer.setSize(window.innerWidth, window.innerHeight);
        document.body.appendChild(renderer.domElement);

        // Додавання лівого моделі
        var leftGeometry = new THREE.BoxGeometry();
        var leftMaterial = new THREE.MeshBasicMaterial({ color: 0x00ff00 });
        var leftModel = new THREE.Mesh(leftGeometry, leftMaterial);
        leftModel.position.x = -2; 
        scene.add(leftModel);

        // Додавання правого моделі
        var rightGeometry = new THREE.BoxGeometry();
        var rightMaterial = new THREE.MeshBasicMaterial({ color: 0xff0000 });
        var rightModel = new THREE.Mesh(rightGeometry, rightMaterial);
        rightModel.position.x = 2; 
        scene.add(rightModel);

        camera.position.z = 5;

        var animate = function () {
            requestAnimationFrame(animate);

            // Додаткові анімації або логіка можуть бути додані тут

            renderer.render(scene, camera);
        };

        animate();
    </script>
</body>
</html>
