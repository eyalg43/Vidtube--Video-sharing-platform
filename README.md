# VidTube Project

VidTube is a full-stack video-sharing platform with both web and Android clients, powered by a Node.js server and a C++ recommendation algorithm. The project is built across four interconnected repositories, each serving a unique function in the system architecture.

## Project Overview

This project is designed to provide a seamless video-streaming experience with recommendations based on a custom algorithm. The system integrates multiple components to serve both web and Android platforms.

## Repositories

The project is split into four main repositories, each handling a different part of the system:

1. **[Web Client Side](https://github.com/maxshabs/project_web/tree/master-part4)**: 
   - Built with React.
   - Provides a user-friendly interface for video browsing, watching, and uploading.

2. **[Android Client Side](https://github.com/eyalg43/project_android/tree/mainPart4)**: 
   - Developed in Java for Android devices.
   - Delivers a native mobile experience for VidTube, with features like video playback, user authentication, and video uploads.

3. **[Node.js Server (Web & Android)](https://github.com/OCDev1/VidTube-server/tree/main-part4)**: 
   - Powers the backend for both web and Android clients.
   - Handles user management, video uploads, API routing, and serves video data to the clients.

4. **[C++ Recommendation Algorithm](https://github.com/maxshabs/vidtube-part4.git)**:
   - A multithreaded C++ server that processes user data to generate personalized video recommendations.
   - Communicates with the Node.js server to suggest videos based on user preferences and popular content.

## Architecture

The system is designed with a **client-server architecture**, where the web and Android clients interact with the Node.js backend. The C++ server is responsible for providing video recommendations, and it communicates with the Node.js server to retrieve and update data.

![Architecture Diagram](link-to-architecture-diagram.png)

## Technologies Used

- **Frontend (Web)**: React, CSS, JavaScript
- **Frontend (Android)**: Java, XML
- **Backend (Server)**: Node.js, Express, MongoDB
- **Recommendation Algorithm**: C++ (multithreaded)

## Features

- **Responsive Web Interface**: Fully responsive web client built with React.
- **Native Android Application**: Android client for mobile users, featuring smooth video playback and user-friendly interactions.
- **Node.js API**: Backend API that handles data persistence, user management, and video handling for both web and Android.
- **Recommendation Algorithm**: A custom C++ algorithm to provide personalized video recommendations based on watch history and popular trends.

## API Documentation

The API enables communication between the client and server for video management, user authentication, and recommendations. Below are some of the key endpoints:

### 1. User Authentication
- **Login**: `POST /auth/login`
- **Register**: `POST /auth/register`

### 2. Video Management
- **Get Video**: `GET /videos/:id`
- **Upload Video**: `POST /videos`

### 3. Recommendation System
- **Get Recommendations**: `POST /recommendations`

Full API documentation is available [here](link-to-api-documentation).
