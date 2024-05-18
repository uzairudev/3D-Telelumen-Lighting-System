

# Three.js WebGL Platform Model

## Overview
This project demonstrates a 3D platform model created using Three.js. It includes features like various types of lights, a VR interface, and GUI controls for manipulating the model and its properties.

## Features
- 3D platform model with detailed structure
- Interactive VR support using `VRButton`
- Real-time controls for changing lights (Directional, Point, Spot, Hemisphere)
- GUI for modifying material properties, shadows, and light settings
- Responsive design to adapt to different screen sizes

## Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/your-username/threejs-platform-model.git
    cd threejs-platform-model
    ```

2. Ensure you have a local web server to run the project. You can use `http-server` for this purpose:
    ```bash
    npm install -g http-server
    http-server
    ```

3. Open the project in your browser:
    ```bash
    http://localhost:8080
    ```

## Usage

- **Navigate**: Use your mouse to orbit around the model. 
- **Change Light**: Use the GUI to switch between different types of lights (Directional, Point, Spot, Hemisphere).
- **Adjust Light Properties**: Use the GUI sliders to adjust the intensity, distance, color, and position of the lights.
- **Modify Materials**: Use the GUI controls to change the color, reflectivity, transparency, and other material properties of the objects in the scene.
- **Toggle Shadows**: Enable or disable shadows using the GUI.

## Dependencies

- [Three.js](https://threejs.org/)
- [OrbitControls](https://threejs.org/docs/#examples/en/controls/OrbitControls)
- [RectAreaLightHelper](https://threejs.org/docs/#examples/en/helpers/RectAreaLightHelper)
- [VRButton](https://threejs.org/docs/#examples/en/webxr/VRButton)
- [HTMLMesh](https://threejs.org/docs/#examples/en/interactive/HTMLMesh)
- [InteractiveGroup](https://threejs.org/docs/#examples/en/interactive/InteractiveGroup)
- [XRControllerModelFactory](https://threejs.org/docs/#examples/en/webxr/XRControllerModelFactory)
- [lil-gui](https://github.com/georgealways/lil-gui)


