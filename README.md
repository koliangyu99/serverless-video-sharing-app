# Serverless Video Sharing App

**Spring 2025 | GitHub**

A full-stack platform for uploading, transcoding, and streaming videos built with modern web technologies.

---

## Overview

The Serverless Video Sharing App is a scalable, secure, and highly available platform designed for video hosting. It allows users to upload videos which are then transcoded and streamed through a responsive web interface. The project leverages a serverless architecture to efficiently manage storage, processing, and messaging.

---

## Features

- **Video Hosting:**  
  Build a robust platform for uploading, transcoding, and streaming videos using Next.js and Firebase.
  
- **Cloud Architecture:**  
  Utilize Google Cloud Storage, Pub/Sub, and Cloud Run to manage storage, messaging, and processing tasks.
  
- **Secure Authentication:**  
  Implement Firebase Auth to provide secure user login, upload, and playback access.
  
- **Serverless Backend:**  
  Design a scalable API using Firebase Functions and Firestore for metadata storage.
  
- **Media Processing:**  
  Leverage FFmpeg within Docker containers to transcode videos on demand and serve them via the hosted client.

---

## Demo & Architecture

### Demo

*Note: The demo is not publicly hosted to mitigate potential legal issues related to user-uploaded content.*

- List videos
- Watch a video
- Sign in/out
- Upload a video
- View the transcoded video

### Architecture

The application is built on a modern, serverless architecture with the following key components:

- **Cloud Storage:**  
  Stores both raw and processed videos uploaded by users.

- **Pub/Sub:**  
  Acts as the messaging service to trigger the video processing workflow.

- **Cloud Run:**  
  Hosts a non-public video processing service. Videos are transcoded using FFmpeg in Docker containers and then uploaded back to Cloud Storage.

- **Cloud Firestore:**  
  Maintains metadata for the videos.

- **Next.js App:**  
  Deployed on Cloud Run, it serves as the web client (similar to YouTube) for browsing and watching videos. The application communicates with Firebase Functions through API calls.

- **Firebase Functions:**  
  Handles API requests by fetching video metadata from Cloud Firestore and serving the required data.

For further details, refer to the [short design document](./DESIGN_DOC.md).

---

## Tech Stack

- **Programming Language:** TypeScript
- **Frontend:** Next.js
- **Backend:** Express.js, Firebase Functions, Cloud Run
- **Media Processing:** FFmpeg (within Docker containers)
- **Authentication:** Firebase Auth
- **Database:** Firebase Firestore
- **Storage:** Google Cloud Storage
- **Messaging:** Google Cloud Pub/Sub

---

## Getting Started

Follow these steps to set up the project locally:

1. **Clone the repository:**

   ```bash
   git clone https://github.com/koliangyu99/serverless-video-sharing-app.git
   cd serverless-video-sharing-app
