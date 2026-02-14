# Google-Cloud-Build-Container-Pipeline
# Cloud Build Container Pipeline (Google Cloud)

## Overview
This project demonstrates how to build, test, and store Docker container images using **Google Cloud Build** and **Artifact Registry**. The goal is to showcase a cloud‑native CI workflow where container images are built and validated in a fully managed environment without relying on local Docker installations.

## Architecture Overview
Source code is packaged into a Docker image using Cloud Build, which executes containerized build steps. The resulting image is stored in Artifact Registry, enabling secure and versioned distribution for downstream deployment targets such as Kubernetes or Cloud Run.

