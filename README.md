# AgeSense — Intelligent Real-Time Facial Age & Gender Estimation

### Bringing Computer Vision and On-Device Artificial Intelligence into a Seamless Mobile Experience.

**AgeSense** is an AI-powered mobile application that transforms live camera input into real-time facial insights through an integrated computer vision and deep learning pipeline.

Engineered with **Flutter, Google ML Kit, and TensorFlow Lite**, AgeSense detects multiple faces, extracts facial regions, and executes dedicated machine learning models directly on the device to estimate age and classify gender — delivering an interactive analysis experience with minimal inference latency and no dependency on a remote prediction server.

More than a facial analysis application, AgeSense demonstrates the practical integration of **Mobile Engineering, Real-Time Image Processing, Computer Vision, and Edge AI** within a unified software solution.

---

## ✦ Core Capabilities

AgeSense brings together intelligent analysis, efficient processing, and a feature-rich mobile experience.

| Capability | Description |
|---|---|
| **Live Facial Intelligence** | Continuously analyzes camera frames and generates age and gender predictions in real time. |
| **Edge AI Processing** | Executes TensorFlow Lite models locally, reducing reliance on network connectivity for inference. |
| **Multi-Face Intelligence** | Detects and analyzes multiple faces within the same camera frame. |
| **Image-Based Analysis** | Extends facial analysis beyond live streaming through gallery image selection. |
| **Persistent Prediction History** | Maintains previous analysis records using a local SQLite database. |
| **Secure User Authentication** | Integrates Firebase Authentication with Email/Password and Google Sign-In. |
| **Adaptive User Experience** | Supports dark and light themes for a customizable interface. |
| **Multilingual Experience** | Incorporates Flutter localization for multi-language support. |

---

## ✦ Inside the Intelligence Pipeline

At the heart of AgeSense lies a carefully structured processing workflow that transforms raw visual input into meaningful model predictions.

### 01 — Real-Time Visual Acquisition

The pipeline begins with a continuous stream of image frames captured through the device camera.

Using Flutter's Camera API, the application:

- Acquires live camera frames through `startImageStream()`.
- Handles YUV420 and BGRA8888 image formats.
- Controls frame processing frequency through throttling.
- Manages asynchronous execution to maintain interface responsiveness.
- Accounts for sensor orientation, camera mirroring, and preview scaling.

A dedicated coordinate-mapping mechanism aligns detected facial regions with their exact positions on the displayed camera preview.

### 02 — Intelligent Facial Detection

Powered by **Google ML Kit Face Detection**, AgeSense identifies facial regions before passing them to the prediction stage.

The detection layer is optimized for real-time operation and provides:

- Facial localization through bounding-box coordinates.
- Simultaneous detection of multiple faces.
- Efficient extraction of facial regions.
- A structured input for downstream machine learning inference.

### 03 — Deep Learning & Model Inference

AgeSense integrates two dedicated **TensorFlow Lite models**, enabling independent age estimation and gender classification directly on the mobile device.

| Model | Input Specification | Task |
|---|---|---|
| Age Model | 200 × 200 RGB | Age Estimation |
| Gender Model | 128 × 128 RGB | Gender Classification |

**The inference lifecycle:**

1. **Facial Extraction** — Isolating each detected face from the original frame.
2. **Image Transformation** — Resizing facial images to match model input specifications.
3. **Pixel Normalization** — Preparing numerical input values within the required range.
4. **Parallelized Processing** — Offloading computational operations through Flutter isolates.
5. **TensorFlow Lite Execution** — Running model inference locally.
6. **Prediction Interpretation** — Processing model outputs and preparing the results for presentation.

This architecture separates facial detection from model inference, creating a modular processing pipeline that can accommodate different model implementations.

### 04 — Real-Time Visual Intelligence

The results are brought to life through a dynamic camera interface that visually connects detected faces with their corresponding predictions.

A custom Flutter `CustomPainter` powers the visualization layer, rendering facial bounding boxes and prediction labels over the live camera preview.

The interface combines:

- Layered rendering through Flutter's `Stack` widget.
- Dynamic facial annotations.
- Continuous prediction updates.
- Asynchronous image processing.
- Responsive visual feedback.

---

## ✦ Technology & Engineering Stack

The application combines a modern mobile framework with specialized machine learning and computer vision technologies.

| Engineering Domain | Technology |
|---|---|
| Mobile Application | Flutter & Dart |
| Computer Vision | Google ML Kit |
| Deep Learning Runtime | TensorFlow Lite |
| Model Architecture | MobileNetV3 |
| Camera & Streaming | Flutter Camera |
| Image Processing | Dart Image Package |
| State Management | Provider |
| Local Data Persistence | SQLite & Sqflite |
| Authentication | Firebase Authentication |
| Identity Integration | Google Sign-In |
| Cloud Services | Firebase Storage |
| Application Preferences | Shared Preferences |

---

## ✦ Software Architecture

AgeSense follows a modular code organization that separates camera operations, machine learning processing, data persistence, authentication, and presentation responsibilities.

```text
lib/
├── main.dart
├── camera_analysis_screen.dart
├── face_painter.dart
├── home_screen.dart
├── history_screen.dart
├── analysis_details_screen.dart
│
├── core/
│   ├── database_helper.dart
│   └── image_isolate_processor.dart
│
├── providers/
│   └── history_provider.dart
│
├── services/
│   └── auth_service.dart
│
├── settings/
└── widgets/
```

**Architectural Highlights**

- Separation of application responsibilities.
- Dedicated services for authentication and persistence.
- Independent image-processing components.
- Provider-based history state management.
- Reusable UI components and custom visualization.

---

## ✦ Installation & Configuration

### Requirements

- Flutter SDK 3.10+
- Compatible Dart SDK
- Android Studio or Xcode
- Configured Firebase project
- Android or iOS development environment

### 1. Clone the Repository

```bash
git clone <repository-url>
cd <project-directory>
```

### 2. Install Dependencies

```bash
flutter pub get
```

### 3. Configure Firebase

Set up a Firebase project and register the required mobile applications.

- Configure Android using `google-services.json`.
- Configure iOS using `GoogleService-Info.plist`.
- Enable the required authentication providers.
- Configure additional Firebase services used by the application.

### 4. Verify Model Assets

Ensure the following TensorFlow Lite models are included and correctly declared in `pubspec.yaml`.

```text
assets/
├── age_model.tflite
└── gender_model.tflite
```

### 5. Launch the Application

```bash
flutter run
```

---

## ✦ Data Management & Privacy

AgeSense is designed around on-device machine learning inference.

Facial detection, image preprocessing, and model execution take place locally on the device, while prediction history is maintained through SQLite.

Firebase services support the application's authentication and configured cloud functionality.

Cloud data handling depends on the enabled Firebase operations and application configuration.

---

## ✦ Engineering Highlights

AgeSense represents the integration of several important areas of software development:

- **Edge AI:** Deploying machine learning models within a mobile application.
- **Computer Vision:** Detecting and extracting multiple facial regions.
- **Real-Time Processing:** Managing continuous camera streams and computational workloads.
- **Mobile Performance:** Using asynchronous processing and isolates.
- **Software Architecture:** Organizing application logic into dedicated components.
- **Data Management:** Combining local persistence with Firebase services.
- **Cross-Platform Development:** Building a unified mobile experience with Flutter.

---

## ✦ Project Information

| Attribute | Details |
|---|---|
| Project | AgeSense |
| Type | Computer Science Graduation Project |
| Domain | Artificial Intelligence & Mobile Development |
| Primary Framework | Flutter |
| AI Technologies | TensorFlow Lite & Google ML Kit |
| Model Family | MobileNetV3 |
| Development Focus | Real-Time Facial Analysis |
| Academic Evaluation | Excellent |
|Role   | Team Leader (7- Member Team ) |

---

<p align="center">

**AGE SENSE**

*Intelligence at the intersection of Computer Vision and Mobile Engineering.*

**Built with Flutter · Powered by Deep Learning · Designed for Real-Time Intelligence**

</p>
