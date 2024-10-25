# Pelvis
Unity Project - Pelvis Visualization

Project Overview

This Unity project provides an interactive visualization tool for exploring a 3D model of the pelvis. The project includes multiple functionalities to manipulate and interact with the model using various tools, including clipping planes, keyboard, mouse controls, and interactive UI elements. The goal is to provide an intuitive and informative way to examine the pelvis model, allowing users to dynamically adjust views and explore different cross-sectional parts of the anatomy.

Installation and Setup

Prerequisites

Unity version: 2021.3.6f1

Coded in IOS

Steps to Run the Project

Clone or Download the Repository: Clone this repository or download the project as a ZIP file.

Open Unity: Launch Unity Hub and open the project folder in the Unity Editor.

Set Up Scenes: Open the main scene (PelvisVisualizationScene) that contains the pelvis model and all functionalities.

Run the Scene: Click the Play button in Unity to interact with the model.

How to Use

Moving and Rotating the Pelvis

Rotate the Pelvis: Hold the left mouse button and press the "P" key, then drag the mouse to rotate the pelvis model.

Translate the Pelvis: Hold the right mouse button and drag the mouse to move the pelvis model in the scene.

Scale/Zoom the Pelvis: Use the scroll wheel to zoom in/out the pelvis model.

Clipping with Planes

Positioning: Click and drag the clipping planes using the mouse to adjust their location. 

Rotation: Hold the "R" key and drag the mouse to rotate the clipping planes if needed.

Code Documentation

Clipping.cs

The Clipping script is responsible for dynamically updating the position and orientation of a clipping plane in real time by interacting with a shader assigned to the clippingMaterial. For each frame, the script calculates the normal vector and position of the assigned clippingPlane object, and sends this information to the shader via the _ClipPlane parameter. This allows the shader to effectively determine which portions of the pelvis model should be visible or hidden, depending on the plane's position. This provides a highly customizable clipping mechanism that reacts immediately to user adjustments, enabling intuitive exploration of different cross-sections of the model.

ClippingPlaneControl.cs

The ClippingPlaneControl script provides interactive control for moving and rotating the clipping plane using a combination of mouse and keyboard inputs. Users can click and drag the clipping plane to adjust its position, while holding the "R" key allows for rotating the plane about its local axes using mouse movement. The plane's position and orientation can be adjusted intuitively, enabling precise control over the cross-sectional views of the pelvis model. The script ensures that the plane movement is limited to certain axes, thereby avoiding unintended changes in depth, which helps maintain visibility and usability during interaction.

RotatePelvis.cs

The RotatePelvis script enables users to interact with the pelvis model through rotation, translation, and scaling, providing a comprehensive way to examine different angles and details. The model can be rotated by holding the left mouse button along with the "P" key, allowing for intuitive manipulation. Users can also translate the pelvis using the right mouse button, enabling movement along the X and Y axes for better positioning within the scene. Additionally, scaling functionality is provided through the mouse scroll wheel, allowing users to zoom in or out to closely inspect or get a broader view of the pelvis. Adjustable speed parameters (rotationSpeed, translationSpeed, scalingSpeed) make it easy to fine-tune the interaction experience for different users or contexts.

DragPoint.cs

The DragPoint script allows users to click and drag specific points in the scene, such as start and end points on the pelvis model. When the user clicks on a point (OnMouseDown), the script calculates an offset between the object's current position and the mouse position, enabling smooth dragging without abrupt jumps. During dragging (OnMouseDrag), the script continuously updates the point's position based on mouse movement, restricted by the calculated offset. This functionality is particularly useful for precisely positioning reference points or control handles in the scene, providing an intuitive and fluid user experience during interaction.

ScrewPath.cs

The ScrewPath script is used to visually represent the path between two specific points in the scene, such as the start and end positions for a screw. This script utilizes a LineRenderer component to draw a line between the assigned startPoint and endPoint. Additionally, the script dynamically calculates the distance between these two points and displays it using a TextMesh component that is positioned at the midpoint of the line. This functionality provides users with real-time visual feedback about the connection and distance between key reference points, which is particularly useful for precision tasks or measurements in the model. The distance text always faces the camera for easy readability, ensuring an intuitive visualization experience.


