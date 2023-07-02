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

## Usage
1. Obtain an API key from Roboflow and replace 'CYzBf27ICRht54nH9vqB' with your API key:
   ```python
   api_key = "YOUR_API_KEY"

2. Run the narrate_room() function with the path to your image file:
   ```python
   image = "path/to/your/image.jpg"
   room = get_room_type(image)
   labels = get_items_in_room(image)
   room_type = room["predictions"][0]["top"]
   narrate_room(room_type, labels)

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






