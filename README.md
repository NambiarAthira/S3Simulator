# S3Simulator-A-benchmarking-Side-Scan-Sonar-simulator-dataset-for-Underwater-Image-Analysis


Kamal Basha S , [Athira. M. Nambiar](https://www.srmist.edu.in/faculty/dr-athira-m-nambiar/)

[[Paper](https://arxiv.org/abs/2408.12833)]


Acoustic sonar imaging systems are widely used for under-
water surveillance in both civilian and military sectors. However, the
acquisition of high-quality sonar datasets for training Artificial Intelli-
gence (AI) models confronts challenges such as limited data availability,
financial constraints and data confidentiality. To overcome these chal-
lenges, we propose a novel benchmark dataset of Simulated Side-Scan
Sonar images, which we term as ‘S3Simulator dataset’. Our dataset
creation utilizes advanced simulation techniques to accurately replicate
underwater conditions and produce diverse synthetic sonar imaging. In
particular, the cutting-edge AI segmentation tool i.e. Segment Anything
Model (SAM) is leveraged for optimally isolating and segmenting the ob-
ject images, such as ships and planes, from real scenes. Further, advanced
Computer-Aided Design tools i.e. SelfCAD, and simulation software such
as Gazebo are employed to create the 3D model and to optimally visualize
within realistic environments, respectively. Further, a range of compu-
tational imaging techniques are employed to improve the quality of the
data, enabling the AI models for the analysis of the sonar images. Exten-
sive analyses are carried out on S3simulator as well as real sonar datasets
to validate the performance of AI models for underwater object classifi-
cation. Our experimental results highlight that the S3Simulator dataset
will be a promising benchmark dataset for research on underwater image
analysis.


# Architecture of S3Simulator
![archi](https://github.com/user-attachments/assets/db8a0d68-27af-4083-afc2-735320f32171)

### Software Versions and Links


| Software                        | Version              | Link                                      |
|----------------------------------|----------------------|-------------------------------------------|
| **Gazebo Multi-Robot Simulator** | 11.10.2              | [Gazebo](https://gazebosim.org/home)      |
| **Ubuntu**                       | 22.04.4 LTS          |                                           |
| **Codename**                     | Jammy                |                                           |
| **SelfCAD**                      | N/A                  | [SelfCAD](https://www.selfcad.com/)       |
| **Segment Anything Model (SAM)** | N/A                  | [Segment Anything](https://segment-anything.com/) |



# Accessing the Segment Anything Model (SAM)
For this project, we utilized the Segment Anything Model (SAM), an advanced AI segmentation tool, to segment silhouette images for 3D modeling. Specifically, SAM was used to isolate objects such as ships and planes from the background for the creation of 3D models in SelfCAD.

We used the [SAM online demo](https://segment-anything.com/demo) to upload silhouette images and segment the required objects.

Steps:
1. Visit the [SAM online demo](https://segment-anything.com/demo).
2. Upload your silhouette image (e.g., ships, planes).
3. Use the intuitive SAM interface to mark and segment the object.
4. Export the segmented mask for further use in 3D modeling with SelfCAD.
5. This approach helped streamline the process of preparing images for 3D modeling and simulation in Gazebo.


# 3D Modeling with SelfCAD
After segmenting the silhouette images using Segment Anything Model (SAM), we used SelfCAD, a powerful browser-based 3D modeling tool, to convert the 2D segmented images into 3D models.

SelfCAD was instrumental in creating detailed 3D models of objects like ships and planes, which were later used in the sonar simulation process in Gazebo.

Steps:
1. Visit [SelfCAD](https://www.selfcad.com/).
2. Import the 2D segmented mask generated by SAM.
3. Use SelfCAD's intuitive 3D sculpting tools to convert the 2D image into a 3D model. Adjust parameters like size, shape, and texture to match real-world objects.
4. Export the 3D model in a format suitable for further simulation (e.g., .stl or .obj).
5. By using SelfCAD, we ensured that the generated models accurately represent real-world objects, making the simulation in Gazebo more realistic.

# Sonar Simulation with Gazebo
Gazebo is an open-source 3D robotics simulator that we used to simulate sonar images with realistic underwater environments. After generating the 3D models using SelfCAD, we imported them into Gazebo to simulate sonar effects such as shadows, noise, and varying seabed terrain.

## Steps to Set Up Gazebo:

1. Install Gazebo: Follow the instructions below to install Gazebo on Ubuntu:

```
# Add the Gazebo repository to your system's sources list
sudo sh -c 'echo "deb http://packages.osrfoundation.org/gazebo/ubuntu-stable $(lsb_release -cs) main" > /etc/apt/sources.list.d/gazebo-stable.list'

# Add the Gazebo key
wget https://packages.osrfoundation.org/gazebo.key -O - | sudo apt-key add -

# Update the package list
sudo apt-get update

# Install Gazebo version 11
sudo apt-get install gazebo11
```

Once installed, you can verify the installation by running:

```
gazebo
```

2. Load the 3D Models: Import the .obj models from the models/ directory into your Gazebo environment. Use the SDF (Simulation Description Format) file to reference the 3D models and place them within the simulation environment.

