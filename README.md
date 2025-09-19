# AI Image Reverse & Generation Tool

Author: Guahunyo

Tutorial video:[点击这里观看视频](https://www.youtube.com/watch?v=hD0BmDEHroU)

## Overview

This project is a powerful tool that integrates with your browser to provide a unique image analysis and generation workflow. It allows users to right-click on any image on a webpage, automatically generate a descriptive prompt for that image, and then use that prompt to create a new set of AI-generated images.

The entire process is displayed in a clean, user-friendly modal window directly on the current page, providing a seamless experience without navigating away.

## Features

- **Browser Integration**: Adds a "反推生图" (Reverse Image & Generate) option to the right-click context menu for images.
- **Reverse Image to Prompt**: Automatically analyzes the selected image and generates a detailed text prompt describing its content.
- **AI Image Generation**: Uses the generated prompt to create four new, unique images using an AI model.
- **Interactive Modal UI**:
  - Displays the original image for reference.
  - Shows the generated text prompt.
  - Presents the four new images with a main image viewer and clickable thumbnails.
  - Allows easy switching between the generated images.
- **Client-Server Architecture**: A Python Flask backend handles the heavy lifting of AI processing, while a lightweight browser extension provides the frontend interface.

## Technology Stack

- **Backend**: Python, Flask
- **Frontend**: JavaScript (for the browser extension), HTML, CSS
- **Core Logic**:
  - `image_analyzer.py`: Handles the logic for reversing an image to a text prompt.
  - `routes.py`: Defines the API endpoints for image analysis and generation.
- **Browser Extension**: Built using standard WebExtension APIs (`manifest.json`, `background.js`, `content.js`).

## Project Structure

```
/
├── extension/            # Browser extension source code
│   ├── scripts/
│   │   ├── background.js # Handles context menu creation
│   │   └── content.js    # Injects the modal and handles API calls
│   └── manifest.json     # Extension configuration
├── static/               # Static assets for the web interface
├── templates/            # HTML templates for the web interface
├── image_analyzer.py     # Core logic for image-to-prompt
├── routes.py             # Flask API route definitions
├── web_app.py            # Main Flask application entry point
└── requirements.txt      # Python dependencies
```

## Setup and Installation

1.  **Install Python Dependencies**:
    Make sure you have Python 3 installed. Then, install the required packages using pip:
    ```bash
    pip install -r requirements.txt
    ```

2.  **Run the Backend Server**:
    Start the Flask server from the project root directory:
    ```bash
    python web_app.py
    ```
    The server will start on `http://127.0.0.1:5000`.

3.  **Load the Browser Extension**:
    - Open your browser (e.g., Chrome, Edge).
    - Navigate to the extensions management page (e.g., `chrome://extensions`).
    - Enable "Developer mode".
    - Click "Load unpacked" and select the `extension` folder from this project.

## How to Use

1.  Navigate to any webpage containing an image you want to use.
2.  Right-click on the desired image.
3.  Select "反推生图" from the context menu.
4.  A modal window will appear. It will first show the generated prompt and then display the four newly generated images.
5.  You can click on the thumbnails at the bottom to view each generated image in the main display area.
