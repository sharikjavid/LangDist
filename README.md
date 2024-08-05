# LangDist: Distributed Training Framework for Large Language Models

## Overview

LangDist is a scalable distributed training framework for Large Language Models (LLMs) built on Ray. It efficiently trains LLMs across multiple devices, utilizing Ray's powerful distributed computing capabilities.

## Features

- **Distributed Training**: Parallel training across multiple devices.
- **Ray Integration**: Efficient task distribution and execution with Ray.
- **FastAPI Backend**: API for device registration, task submission, and status monitoring.
- **Model and Dataset Management**: Simple upload and management of models and datasets.
- **React Frontend**: User-friendly interface for interacting with the training system.
- **Flexible Model Support**: Compatible with various LLM architectures, including LLaMA.

## System Architecture

LangDist is composed of the following components:

1. **Backend API** (`main.py`): FastAPI server for handling device registration, task submission, and status queries.
2. **Ray Setup** (`ray_setup.py`): Configures and initializes the Ray cluster.
3. **Training Module** (`train.py`): Implements distributed training logic using Ray.
4. **Data Loader** (`dataloader.py`): Handles loading and preprocessing of datasets.
5. **Model Loader** (`model.py`): Manages loading and initialization of LLM models.
6. **Frontend** (`App.tsx`): React-based user interface for interacting with the system.

## Installation

1. Clone the repository:
   ```sh
   git clone https://github.com/yourusername/LangDist.git
   cd LangDist
   ```

## Installation

2. Install the required Python packages:

   ```
   pip install -r requirements.txt
   ```

3. Install Node.js and npm (for the frontend).

4. Install frontend dependencies:
   ```
   cd frontend
   npm install
   ```

## Usage

### Starting the Backend

1. Navigate to the project root directory.
2. Run the FastAPI server:
   ```
   uvicorn main:app --host 0.0.0.0 --port 8000
   ```

### Starting the Frontend

1. Navigate to the `frontend` directory.
2. Start the React development server:
   ```
   npm start
   ```

### API Endpoints

        "POST /devices/register: Register a new device for distributed training.",
        "GET /devices: List all registered devices.",
        "POST /tasks/submit: Submit a new training task.",
        "GET /tasks: List all submitted tasks.",
        "GET /tasks/{task_id}/status: Check the status of a specific task.",
        "POST /upload/model/: Upload a custom model file.",
        "POST /upload/dataset/: Upload a custom dataset file."

### Distributed Training

"1. Register available devices using the /devices/register endpoint.",
"2. Upload your model and dataset using the respective upload endpoints.",
"3. Submit a training task via the /tasks/submit endpoint, specifying the model, dataset, and devices to use.",
"4. Monitor the task status using the /tasks/{task_id}/status endpoint."

## Development

### Running Tests

"Execute the test suite to ensure system integrity:",
" pytest test_main.py test_ray.py"
