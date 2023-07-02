# Roboflow Image Recognition

This project utilizes Roboflow API and image recognition models to identify the type of room and objects present in an image. It provides a narration of the room type and objects detected.

## Prerequisites

- Python 3.6+
- `pyttsx3` library
- `roboflow` library

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/your-username/your-repository.git
   ```
2.Install the required libraries:
   ```bash
   pip install pyttsx3 roboflow
   ```
## Setting Up Roboflow

Setting up Roboflow is simple:

1. Create an account on Roboflow.
2. After signing up and logging in, click on the "Get API Key" button on the dashboard to get your API key.
3. Set up the 'mit-indoor-scene-recognition' project on your Roboflow account. This project is used for room type recognition.

You will then be able to use the Roboflow API in your Python scripts by initializing it with your API key:

```python
api_key = "YOUR_ROBOFLOW_API_KEY"
rf = roboflow.Roboflow(api_key)
```
## Usage
 Run the narrate_room() function with the path to your image file:
   ```python
   image = "path/to/your/image.jpg"
   room = get_room_type(image)
   labels = get_items_in_room(image)
   room_type = room["predictions"][0]["top"]
   narrate_room(room_type, labels)
   ```
## Functions

### `get_room_type(image_file: str) -> dict`

Get the type of room a photo was taken in (e.g., kitchen, living room). It uses the Roboflow API and the `mit-indoor-scene-recognition` model.

- `image_file`: Path to the image file.

### `get_items_in_room(image: str) -> list`

Find items present in a room image. It uses the Roboflow API and the `all_finalize` model.

- `image`: Path to the image file.

### `narrate_room(room_type: str, labels: list) -> None`

Speak out the type of room a photo was taken in and the objects in the room.

- `room_type`: Type of the room (e.g., kitchen, living room).
- `labels`: List of objects detected in the room.

## Explanation of Functions

- `get_room_type(image)`: This function takes an image filename as input and uses Roboflow's 'mit-indoor-scene-recognition' model to predict the type of room in the image. It returns a dictionary with the prediction details.

- `get_items_in_room(image)`: This function also takes an image filename as input. It uses another pre-trained Roboflow model to detect objects in the room. It returns a list of the detected objects.

- `narrate_room(room_type, labels)`: This function takes the type of room and the list of detected objects as input. It uses the pyttsx3 text-to-speech engine to speak out the type of room and the objects within it.







