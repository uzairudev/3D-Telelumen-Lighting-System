
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

## Example Code

**Vertex Shader**:
```glsl
varying vec2 vUv;
void main() {
    vUv = vec2( uv.x, 1.0-uv.y );
    gl_Position = projectionMatrix * modelViewMatrix * vec4(position, 1.0);
}
```

**Fragment Shader Example (Laplacian Filter)**:
```glsl
precision highp float;
uniform sampler2D image;
uniform vec2 resolution;
varying vec2 vUv;

void main() {
    vec2 offset = 1.0 / resolution;
    vec4 sum = vec4(0.0);
    vec4 texel = texture2D(image, vUv);

    float kernel[9];
    kernel[0] = -1.0; kernel[1] = -1.0; kernel[2] = -1.0;
    kernel[3] = -1.0; kernel[4] = 8.0;  kernel[5] = -1.0;
    kernel[6] = -1.0; kernel[7] = -1.0; kernel[8] = -1.0;

    for (int i = -1; i <= 1; i++) {
        for (int j = -1; j <= 1; j++) {
            vec4 neighbor = texture2D(image, vUv + vec2(i, j) * offset);
            sum += neighbor * kernel[(i + 1) * 3 + (j + 1)];
        }
    }

    sum /= 9.0;
    sum += texel;

    gl_FragColor = sum;
}
```

**HTML Setup**:
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, user-scalable=no, minimum-scale=1.0, maximum-scale=1.0" />
    <style>
      body {
        margin: 0;
        padding: 0;
        width: 100%;
        height: 100%;
        background-color: #aaaaaa;
        overflow: hidden;
      }
      body {
        font-family: Monospace;
        margin: 0px;
        overflow: hidden;
      }
    </style>
  </head>
  <body>
    <script id="vertShader" type="shader">
      varying vec2 vUv;
      void main() {
          vUv = vec2( uv.x, 1.0-uv.y );
          gl_Position = projectionMatrix * modelViewMatrix * vec4(position, 1.0);
      }
    </script>

    <script async src="https://unpkg.com/es-module-shims@1.3.6/dist/es-module-shims.js"></script>
    <script type="importmap">
      {
        "imports": {
          "three": "https://unpkg.com/three@0.149.0/build/three.module.js",
          "three/addons/": "https://unpkg.com/three@0.149.0/examples/jsm/"
        }
      }
    </script>

    <script type="module" src="sanfrancisco.js"> </script>
  </body>
</html>
```

## References

- [Basic Theory of Physically Based Rendering](https://marmoset.co/posts/basic-theory-of-physically-based-rendering/)
- [Three.js Materials Documentation](https://threejs.org/manual/#en/materials)
- [Three.js Lighting Documentation](https://threejs.org/manual/#en/lights)
- [lil-gui Documentation](https://lil-gui.georgealways.com/)

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more information.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any bugs or enhancements.

## Contact

For any questions or feedback, please reach out to [your-email@example.com](mailto:your-email@example.com).

---

Feel free to customize this README further based on your specific needs and preferences.
