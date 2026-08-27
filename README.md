# Media Service

## Overview
The **Media Service** is a specialized backend microservice responsible for handling all file and media uploads within the Cloud Trip Gallery application. It processes binary data such as trip photos and travel log images.

## Technical Details
* **Technology Stack**: Java 25, Spring Boot, Spring Web
* **Default Port**: `8083`
* **Service Registry**: Discovers and registers via Eureka Server.
* **Configuration**: Pulls startup configurations from the Config Server.

## Key Responsibilities
* **File Upload Processing**: Exposes REST endpoints (e.g., `/media/upload`) to securely accept multipart file uploads from the frontend.
* **Storage Integration**: Saves media assets securely (e.g., to local storage or Cloud Storage buckets) and generates access URLs.
* **File Validation**: Enforces size limits (e.g., 10MB per file) and validates file types to ensure system security and stability.

## Deployment Context
In the GCP environment, this service runs as part of the autoscaling backend group. It works in tandem with the Travel Log service, providing the hosted URLs for images attached to travel memories.
