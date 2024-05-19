
# Telelumen Lighting System in a Cornell Box with Three.js

## Overview

This project showcases a 3D model of the Telelumen lighting system within a Cornell Box using Three.js. The project involves dynamic interaction with the scene through a graphical user interface (GUI), experimenting with various lighting and material properties, and experiencing the setup in VR.

## Features

- **3D Model**:
  - A detailed 3D model of the Telelumen lighting system.
  - Includes a cone, cylinder, and sphere with different materials.

- **Interactive GUI**:
  - Dynamically change the color of the Cornell Box walls.
  - Modify lighting properties (intensity, color, position).
  - Adjust material properties (transparency, shininess, textures).

- **Lighting Options**:
  - Directional light, point light, spot light, and hemisphere light.
  - Ambient light for overall illumination.
  - Rectangular lights to simulate secondary light sources.

- **Shadows**:
  - Realistic shadows with adjustable properties.

- **VR Experience**:
  - Immersive VR mode with interactive GUI controls.

## Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/your-username/telelumen-lighting-cornell-box.git
    cd telelumen-lighting-cornell-box
    ```

2. Install dependencies and start a local web server:
    ```bash
    npm install -g http-server
    http-server
    ```

3. Open the project in your browser:
    ```bash
    http://localhost:8080
    ```

## Usage

### Initial Setup

The Three.js scene is initialized with a black background, a camera positioned to view the model, and a renderer to display the scene. The Cornell Box and Telelumen lighting system are created with grouped geometries.

### Interactive GUI

- **Wall Color**: Change the color of the Cornell Box walls dynamically using the GUI.
- **Lighting**: Use the GUI to select different lighting options and adjust their properties like intensity, distance, and color.
- **Material Properties**: Adjust properties such as color, wireframe, reflectivity, emissive color, depth test, alpha test, opacity, transparency, visibility, roughness, metalness, clear coat, transmission, flat shading, and texture maps.

### Adding Objects

- **Cone**: A cone with `MeshLambertMaterial` is placed on the left side of the table.
- **Cylinder**: A cylinder with `MeshPhongMaterial` is placed on the right side of the table.
- **Sphere**: A sphere with `MeshPhysicalMaterial` is placed in the center of the table.

### Lighting and Shadows

- **Ambient Light**: Adds a soft, overall light to the scene.
- **Point Light**: Positioned above the scene, casting realistic shadows.
- **RectAreaLight**: Simulates the walls as secondary light sources for enhanced realism.
- **Shadow Controls**: Adjust shadow properties like shadow map size and shadow bias.

### VR Experience

- **VR Button**: Activate VR mode with a simple button click.
- **Interactive Group**: GUI controls available in VR for an immersive and interactive experience.



## References

- [Basic Theory of Physically Based Rendering](https://marmoset.co/posts/basic-theory-of-physically-based-rendering/)
- [Three.js Materials Documentation](https://threejs.org/manual/#en/materials)
- [Three.js Lighting Documentation](https://threejs.org/manual/#en/lights)
- [lil-gui Documentation](https://lil-gui.georgealways.com/)

