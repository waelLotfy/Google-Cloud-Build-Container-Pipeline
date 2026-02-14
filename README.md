# Google-Cloud-Build-Container-Pipeline
# Cloud Build Container Pipeline (Google Cloud)

## Overview
This project demonstrates how to build, test, and store Docker container images using **Google Cloud Build** and **Artifact Registry**. The goal is to showcase a cloud‑native CI workflow where container images are built and validated in a fully managed environment without relying on local Docker installations.

## Architecture Overview
Source code is packaged into a Docker image using Cloud Build, which executes containerized build steps. The resulting image is stored in Artifact Registry, enabling secure and versioned distribution for downstream deployment targets such as Kubernetes or Cloud Run.

## Key Concepts Demonstrated
- Dockerfile‑based image creation
- Managed CI pipelines using Cloud Build
- Artifact versioning and secure storage
- Build‑time testing using container exit codes
- Failure propagation in automated pipelines

## Implementation Details

### Container Image
A minimal Alpine Linux base image is used to package a shell‑based application. The container executes a script on startup, simulating application behavior and test outcomes.

### Cloud Build Pipelines
Two build strategies are implemented:

1. **Implicit Build**
   - Uses `gcloud builds submit` with a Dockerfile
   - Automatically builds and pushes the image to Artifact Registry

2. **Declarative Build (cloudbuild.yaml)**
   - Defines explicit build steps
   - Uses Docker as a build tool inside Cloud Build
   - Pushes versioned images to Artifact Registry

### Build‑Time Testing
A second pipeline (`cloudbuild2.yaml`) demonstrates how Cloud Build can execute the newly built container as part of the pipeline. The container intentionally exits with a non‑zero status to simulate test failure, causing the build to fail automatically.

This pattern mirrors real‑world CI/CD behavior where failed tests block deployments.

## Why This Matters
This project reflects modern platform engineering practices:
- Immutable artifacts
- Automated validation
- Infrastructure‑managed CI
- Clear separation between build, test, and deploy stages

These principles are foundational for scalable microservice and Kubernetes‑based systems.

## Technologies Used
- Google Cloud Build
- Artifact Registry
- Docker
- Shell scripting
- Linux container primitives


