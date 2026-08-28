Bariq: A Multi-Modal AI System for Early Glaucoma Screening
Bariq is a mobile health (mHealth) platform developed to facilitate the early detection of Glaucoma using deep learning analysis of fundus images integrated with clinical patient data. The system provides a clinical decision-support tool designed for both ophthalmologists and patients, ensuring data-driven risk assessment and longitudinal health tracking.

### 1. Key Functionalities
Hybrid Diagnostic Engine: Utilizes a weighted ensemble of Convolutional Neural Networks (CNNs) to analyze fundus images, complemented by a clinical risk factor analysis (IOP, Age, Medical History).

Dual-Role Architecture: Specialized interfaces for Healthcare Providers (multi-patient management and longitudinal analysis) and Patients (self-monitoring and screening reminders).

Explainable AI (XAI): Integration of Grad-CAM visualizations to provide clinical interpretability by highlighting pathological regions in the retina.

Data Sovereignty & Privacy: Implementation of a local SQLite infrastructure for secure, offline storage of patient records and diagnostic history.

Automated Clinical Reporting: Generation of standardized PDF medical reports summarizing AI findings and clinical data for professional use.

### 2. Technical Framework
Frontend & State Management
Framework: Flutter (v3.0.0+) for cross-platform deployment.

State Management: Provider Pattern for reactive UI updates and dependency injection.

Localization: Bilingual support (Arabic/English) with specialized RTL layout handling.

Backend & AI Inference
Architecture: Client-Server model via FastAPI/Flask hosted on a GPU-enabled environment.

Inference Protocol: RESTful API using Multipart/Form-data for concurrent image and metadata transmission.

Database: Local relational storage via sqflite and key-value pairs via shared_preferences.

### 3. System Architecture (lib/ directory)
The project adopts a Layered Feature-Driven Architecture to ensure scalability and maintainability:

core/: Centralized themes, global constants, and utility functions.

models/: Strongly typed data structures (e.g., ScanRecord, PatientProfile).

providers/: Business logic layer managing authentication, theme, and data persistence.

services/: Infrastructure layer handling API communication, SQLite CRUD, and PDF generation.

screens/: UI layer organized by functional modules (Diagnosis, Insights, History).

### 4. Deployment & Integration
AI Backend Setup
Model Loading: Load the pre-trained ensemble models (ResNet50, MobileNetV2, VGG16).

Server Initialization: Deploy the Python backend to expose the /predict endpoint.

Tunneling: Establish a secure connection (e.g., Ngrok) and update the baseUrl in api_service.dart.

Installation
Ensure Flutter SDK is configured.

Execute flutter pub get to resolve dependencies.

Deploy to a physical device via flutter run --release for optimal performance.


### Full Project Repository (Extended Implementation)
For a comprehensive review of the project, including high-resolution models, extensive datasets, and full environment configurations that exceed the university's size limitations, please access the complete repository via the link below:

Google Drive Link:(https://drive.google.com/file/d/1qc9vhey59cwGyDDEO-zyaU07ZsRbkcOC/view?usp=sharing)

Contents:

Full Trained Ensemble Models (.h5 files).

Complete Dataset for training and validation.

Pre-configured Google Colab Notebooks.

Full Mobile Application Source Code.

Note: This link serves as the primary source for the "Bariq" system's full implementation and allows for a complete replication of the clinical diagnostic environment.
