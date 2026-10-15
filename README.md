# BoneSpy

### Computer vision for preoperative knee implant templating

**BoneSpy** is a research-stage orthopedic planning prototype that analyzes knee radiographs to support anatomical segmentation, dimensional measurements, and preoperative implant templating. It combines computer vision, image processing, and a browser-based interface to explore faster and more repeatable planning workflows.

> **Portfolio showcase:** This repository contains selected documentation and demonstration media only. The application source code, trained model weights, datasets, clinical images, credentials, and deployment configuration are intentionally not published here. BoneSpy is **not** an approved medical device and is not intended for clinical decision-making.

## Live website

Explore the BoneSpy project at **[BoneSpy.com](https://bonespy.com)**.

## Demonstrations

| Early segmentation prototype | Segmentation development |
|:---:|:---:|
| ![Early BoneSpy web interface showing segmentation output](media/early-segmentation-demo.jpg) | ![Development visualization of knee bone segmentation](media/segmentation-model-debug.jpg) |

**Mobile measurement interface**

![Mobile browser results showing femoral and tibial measurements](media/mobile-measurement-demo.jpg)

**Implant alignment concept**

![Presentation slide showing rotation and translation for implant alignment](media/implant-alignment-presentation.jpg)

The images show different development stages and demonstrations, not a single production release.

## How the system works

1. **Radiograph input:** The application accepts AP and/or lateral knee images, depending on the workflow.
2. **Preprocessing:** Images are prepared for model inference, including geometry and intensity handling as appropriate.
3. **Bone segmentation:** A deep-learning segmentation workflow identifies anatomical regions, including the femur and tibia. Earlier experiments also used YOLOv8 segmentation; later work explored **nnU-Net v2** for anatomy segmentation.
4. **Geometry extraction:** Masks are used to estimate anatomical boundaries and measurements. Pixel-to-millimeter conversion requires an appropriate image scale or calibration.
5. **Template matching:** Digital orthopedic implant templates and size tables are considered against estimated anatomy; rotations and translations align candidate templates with the image.
6. **Visualization:** The web interface displays overlays, measurements, and proposed size/alignment information for research and review.

```text
Knee radiograph(s)
       |
Image preprocessing
       |
Segmentation inference
       |
Anatomical masks and landmarks
       |
Measurements + implant templates
       |
Visual overlay and research output
```

## Technical areas

- **Computer vision:** segmentation, mask processing, image geometry, visualization
- **Machine learning:** YOLOv8 segmentation prototypes and nnU-Net v2 experimentation
- **Backend:** Python-based image-processing and inference services
- **Frontend:** React / TypeScript interfaces and browser visualization
- **Engineering:** API integration, deployment experimentation, research validation, and troubleshooting

## Engineering considerations

- **Calibration:** Measurements from radiographs depend on reliable image scale and acquisition geometry.
- **Generalization:** Segmentation and sizing performance must be validated across image sources, anatomy, and imaging conditions.
- **Privacy:** Actual patient data should not be committed to a public repository; any demonstration imaging must be appropriately sourced and cleared.
- **Clinical safety:** Automated suggestions require independent clinical validation and oversight before any clinical use.

## Development context

BoneSpy was developed as an engineering and medical-imaging research project. Work includes segmentation experiments, an interface for image upload and analysis, and evaluation of digital implant templates for femoral and tibial components.

**Project focus:** computer vision · medical imaging · full-stack prototyping · applied AI

## Source code and demos

The implementation is maintained separately from this **public, code-free portfolio showcase**. This repository is intentionally limited to descriptions and selected visual demonstrations.

---

*Screenshots represent prototype development and are not evidence of clinical accuracy or regulatory clearance.*