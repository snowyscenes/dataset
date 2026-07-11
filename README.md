# Snowyscenes: A Multimodal Multitask Dataset Toward Snow-tonomous Vehicles
![Image examples](./images/ROADVIEW_Snow_Intro_1_rev1.png)
<table>
  <tr>
    <td align="center">
      <img src="images/active-snow.gif" width="300"/>
      <br>
      <sub>Active Snow</sub>
    </td>
    <td align="center">
      <img src="images/urban-no-snowfall.gif" width="300"/>
      <br>
      <sub>No Snowfall </sub>
    </td>
    <td align="center">
      <img src="images/highway-snowfall.gif" width="300"/>
      <br>
      <sub>Highway Snowfall</sub>
    </td>
  </tr>
</table>

# Download

Email to (ms.thienthu.ngo@gmail.com) or (eren.aksoy@cs.lth.se)

## Snowy Scenes Dataset

**Snowy Scenes** is a multimodal multitask autonomous driving dataset designed for robust perception in snowy winter conditions. The dataset was collected in real-world urban and highway scenarios in Espoo, Finland, under accumulated snow, active snowfall, and late-evening snowy driving conditions.

The dataset contains **22,331 synchronized frames** collected over **14.4 km** of driving, with **5,027 expertly annotated LiDAR scans**. The sensor setup includes a high-resolution **128-beam LiDAR**, a front-facing **RGB camera**, three **thermal cameras**, and **GNSS/IMU** data for accurate ego-positioning and synchronization.

### Key Features

- **Real-world snowy driving data**
  - Captured only under snowy winter conditions
  - Includes accumulated snow, falling snow, and highway snow scenarios

- **Multimodal sensor setup**
  - 128-beam Velodyne VLS-128 LiDAR
  - 2.3 MP RGB front-facing camera
  - Three 0.3 MP thermal cameras
  - GNSS/IMU system for localization and synchronization

- **Rich 3D annotations**
  - 5,027 annotated LiDAR scans
  - 27 semantic classes
  - Point-wise semantic labels
  - Falling snowflake annotations
  - 221,081 3D bounding boxes

- **Supported perception tasks**
  - 3D semantic segmentation
  - 3D object detection
  - Point cloud denoising / de-snowing
  - Multitask 3D perception learning

### Dataset Split

The annotated data is split at the scene level:

| Split | Number of Scenes | Percentage |
|---|---:|---:|
| Training | 3,016 | 60% |
| Validation | 1,005 | 20% |
| Testing | 1,006 | 20% |

Each split preserves the same scene distribution: approximately **60% falling snow**, **20% highway snow**, and **20% accumulated snow**.

### Annotation Classes

Snowy Scenes provides point-wise annotations for **27 semantic categories**, including common road-scene classes such as cars, trucks, pedestrians, road, sidewalk, building, vegetation, terrain, traffic signs, poles, and a dedicated class for **falling snowflakes**.

### Benchmark Tasks

The dataset includes benchmark experiments for:

1. **3D Semantic Segmentation**  
   Models such as SalsaNext, PTv3, and Cylinder3D are evaluated. Cylinder3D achieves the highest semantic segmentation performance with an mIoU of **76.38**.
   ![Image examples](./images/Table3.png)

<table>
  <thead>
    <tr>
      <th>Model</th>
      <th>Model</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>SalsaNext</td>
      <td align="center"><a href="PUT_LINK_HERE">link</a></td>
    </tr>
    <tr>
      <td>PTv3</td>
      <td align="center"><a href="PUT_LINK_HERE">link</a></td>
    </tr>
    <tr>
      <td>Cylinder3D</td>
      <td align="center"><a href="PUT_LINK_HERE">link</a></td>
    </tr>
  </tbody>
</table>

2. **Point Cloud De-snowing**  
   The dataset supports binary segmentation of snow particles versus regular LiDAR points. Cylinder3D achieves the strongest supervised de-snowing performance.
  <table>
  <thead>
    <tr>
      <th>Model</th>
      <th>Type</th>
      <th>Precision ↑</th>
      <th>Recall ↑</th>
      <th>F1 ↑</th>
      <th>IOU ↑</th>
      <th>Model</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>SalsaNext</td>
      <td align="center">SL</td>
      <td align="center">74.99 ± 0.46</td>
      <td align="center">86.93 ± 0.12</td>
      <td align="center">80.52 ± 0.32</td>
      <td align="center">67.39 ± 0.44</td>
      <td align="center"><a href="PUT_LINK_HERE">link</a></td>
    </tr>
    <tr>
      <td>Cylinder3D</td>
      <td align="center">SL</td>
      <td align="center">95.87 ± 0.55</td>
      <td align="center">88.20 ± 0.63</td>
      <td align="center">91.87 ± 0.14</td>
      <td align="center">84.96 ± 0.23</td>
      <td align="center"><a href="PUT_LINK_HERE">link</a></td>
    </tr>
    <tr>
      <td>3D-OutDet</td>
      <td align="center">SL</td>
      <td align="center">90.70 ± 0.23</td>
      <td align="center">83.24 ± 0.03</td>
      <td align="center">86.81 ± 0.09</td>
      <td align="center">76.70 ± 0.14</td>
      <td align="center"><a href="PUT_LINK_HERE">link</a></td>
    </tr>
    <tr>
      <td>DROR</td>
      <td align="center">UN</td>
      <td align="center">6.52</td>
      <td align="center">81.84</td>
      <td align="center">12.08</td>
      <td align="center">6.43</td>
      <td align="center"><a href="PUT_LINK_HERE">link</a></td>
    </tr>
    <tr>
      <td>SSR</td>
      <td align="center">UN</td>
      <td align="center">40.23</td>
      <td align="center">74.79</td>
      <td align="center">52.32</td>
      <td align="center">35.43</td>
      <td align="center"><a href="PUT_LINK_HERE">link</a></td>
    </tr>
    <tr>
      <td>LiSnowNet-LI</td>
      <td align="center">UN</td>
      <td align="center">12.34 ± 0.86</td>
      <td align="center">79.76 ± 5.91</td>
      <td align="center">21.25 ± 1.08</td>
      <td align="center">11.90 ± 0.67</td>
      <td align="center"><a href="PUT_LINK_HERE">link</a></td>
    </tr>
    <tr>
      <td>LiSnowNet-L2</td>
      <td align="center">UN</td>
      <td align="center">13.72 ± 0.00</td>
      <td align="center">6.66 ± 0.00</td>
      <td align="center">8.96 ± 0.00</td>
      <td align="center">4.69 ± 0.00</td>
      <td align="center"><a href="PUT_LINK_HERE">link</a></td>
    </tr>
    <tr>
      <td>3D-UnOutDet</td>
      <td align="center">UN</td>
      <td align="center">49.82 ± 1.29</td>
      <td align="center">82.65 ± 0.09</td>
      <td align="center">62.14 ± 0.97</td>
      <td align="center">45.09 ± 1.03</td>
      <td align="center"><a href="PUT_LINK_HERE">link</a></td>
    </tr>
  </tbody>
</table>

3. **3D Object Detection**  
   LiDAR-based and multimodal detection models are benchmarked for car detection. Sensor fusion using LiDAR, RGB, and thermal data improves detection performance.

 <table>
  <thead>
    <tr>
      <th>Method</th>
      <th>Modality</th>
      <th>AP ↑</th>
      <th>ATE ↓</th>
      <th>ASE ↓</th>
      <th>AOE ↓</th>
      <th>Model</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>PointPillars</td>
      <td align="center">L</td>
      <td align="center">75.2</td>
      <td align="center">0.24</td>
      <td align="center">0.063</td>
      <td align="center"><strong>0.280</strong></td>
      <td align="center"><a href="PUT_LINK_HERE">link</a></td>
    </tr>
    <tr>
      <td>CenterPoint</td>
      <td align="center">L</td>
      <td align="center">66.9</td>
      <td align="center">0.24</td>
      <td align="center">0.072</td>
      <td align="center">0.414</td>
      <td align="center"><a href="PUT_LINK_HERE">link</a></td>
    </tr>
    <tr>
      <td>TransFusion-L</td>
      <td align="center">L</td>
      <td align="center"><strong>76.2</strong></td>
      <td align="center">0.23</td>
      <td align="center">0.097</td>
      <td align="center">0.391</td>
      <td align="center"><a href="PUT_LINK_HERE">link</a></td>
    </tr>
    <tr>
      <td>VoxelNeXt</td>
      <td align="center">L</td>
      <td align="center">74.1</td>
      <td align="center"><strong>0.18</strong></td>
      <td align="center">0.064</td>
      <td align="center">0.530</td>
      <td align="center"><a href="PUT_LINK_HERE">link</a></td>
    </tr>
    <tr>
      <td>IA-SSD</td>
      <td align="center">L</td>
      <td align="center">72.1</td>
      <td align="center">0.20</td>
      <td align="center"><strong>0.051</strong></td>
      <td align="center">0.369</td>
      <td align="center"><a href="PUT_LINK_HERE">link</a></td>
    </tr>
    <tr>
      <td>CenterPoint (FOV)</td>
      <td align="center">L</td>
      <td align="center">35.0</td>
      <td align="center">0.62</td>
      <td align="center">0.071</td>
      <td align="center">0.445</td>
      <td align="center"><a href="PUT_LINK_HERE">link</a></td>
    </tr>
    <tr>
      <td>TransBEVFusion</td>
      <td align="center">L</td>
      <td align="center">67.63</td>
      <td align="center">0.37</td>
      <td align="center">0.11</td>
      <td align="center">1.65</td>
      <td align="center"><a href="PUT_LINK_HERE">link</a></td>
    </tr>
    <tr>
      <td>TransBEVFusion</td>
      <td align="center">LC</td>
      <td align="center">77.77</td>
      <td align="center">0.28</td>
      <td align="center">0.12</td>
      <td align="center">1.65</td>
      <td align="center"><a href="PUT_LINK_HERE">link</a></td>
    </tr>
    <tr>
      <td>TransBEVFusion</td>
      <td align="center">LCT</td>
      <td align="center">78.52</td>
      <td align="center">0.28</td>
      <td align="center">0.12</td>
      <td align="center">1.66</td>
      <td align="center"><a href="PUT_LINK_HERE">link</a></td>
    </tr>
        <tr>
      <td>UniTR</td>
      <td align="center">L</td>
      <td align="center">51.23</td>
      <td align="center">0.36</td>
      <td align="center">0.11</td>
      <td align="center">0.14</td>
      <td align="center"><a href="PUT_LINK_HERE">link</a></td>
    </tr>
    <tr>
      <td>UniTR</td>
      <td align="center">LC</td>
      <td align="center">71.74</td>
      <td align="center">0.30</td>
      <td align="center">0.10</td>
      <td align="center">0.89</td>
      <td align="center"><a href="PUT_LINK_HERE">link</a></td>
    </tr>
    <tr>
      <td>UniTR</td>
      <td align="center">LCT</td>
      <td align="center">70.65</td>
      <td align="center">0.30</td>
      <td align="center">0.11</td>
      <td align="center">0.91</td>
      <td align="center"><a href="PUT_LINK_HERE">link</a></td>
    </tr>
  </tbody>
</table>
4. **Multitask Learning**  
   Snowy Scenes also enables joint learning of semantic segmentation and object detection. <p>↑ denotes higher is better.</p>

<table>
  <thead>
    <tr>
      <th>Model</th>
      <th>mIoU ↑</th>
      <th>Car AP ↑</th>
      <th>Model</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center">SSMT-seg (ours)</td>
      <td align="center">53.4</td>
      <td align="center">-</td>
      <td align="center"><a href="PUT_LINK_HERE">link</a></td>
    </tr>
    <tr>
      <td align="center">SSMT-det (ours)</td>
      <td align="center">-</td>
      <td align="center">64.5</td>
      <td align="center"><a href="PUT_LINK_HERE">link</a></td>
    </tr>
    <tr>
      <td align="center">SSMT-joint (ours)</td>
      <td align="center">48.3</td>
      <td align="center">67.2</td>
      <td align="center"><a href="PUT_LINK_HERE">link</a></td>
    </tr>
  </tbody>
</table>

     
### Supplementary Materials

### Citation

Please cite the associated publication when using this dataset:

```bibtex
@ARTICLE{snowy_scenes_dataset,
  author = {Your Name},
  title = {Snowy Scenes Dataset},
  year = {2026},
  journal={IEEE Robotics and Automation Letters}, 
  url = {https://github.com/snowyscenes/dataset}
}
