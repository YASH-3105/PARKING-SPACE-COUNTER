# PARKING-SPACE-COUNTER

A computer vision system that monitors and counts available parking spaces in real-time using OpenCV and CVZone.

## 🎬 Demo

### Demo Video

[![Parking Space Counter Demo](https://via.placeholder.com/600x338?text=Demo+Video+Thumbnail)](https://youtu.be/your-demo-video-id)

*Click the image above to watch the demo video*

### Sample Output

![Sample Output](https://via.placeholder.com/800x450?text=Sample+Output+Screenshot)

*Example of the application detecting and counting available parking spaces*

### How to Run a Demo

To quickly test the project with the included sample data:

1. Clone the repository and install dependencies as described in the Installation section
2. Make sure you have a video file named `carPark.mp4` in the project directory
3. If you want to use the pre-defined parking spaces, ensure the `CarParkPos` file is in the project directory
4. Run `python main.py` to see the detection in action

If you're starting from scratch:
1. Place your parking lot video as `carPark.mp4` in the project directory
2. Run `python ParkingSpacePicker.py` and define the parking spaces by clicking
3. Run `python main.py` to see the detection results

*Note: Replace the placeholder images and video links above with actual screenshots and demo video of your application when available.*

## 📋 Overview

This parking space counter is a simple yet effective solution for monitoring parking lot occupancy using computer vision techniques. Built with Python, OpenCV, and CVZone, the system processes video footage to detect and count available parking spaces in real-time. The application visualizes the results by highlighting vacant spaces in green and occupied ones in red, alongside displaying a counter of available spots.

## ✨ Features

- **Real-time Space Detection**: Automatically monitors predefined parking spaces
- **Occupancy Tracking**: Counts and displays the number of free parking spaces
- **Visual Indicators**: Color-coded overlays showing empty (green) vs. occupied (red) spaces
- **Space Configuration Tool**: Interactive interface to define parking spaces with mouse clicks
- **Image Processing Pipeline**: Multi-stage processing for robust vehicle detection
- **Persistence**: Saves parking space positions between sessions

## 🛠️ Technologies

- **Python**: Core programming language
- **OpenCV**: Computer vision and image processing
- **CVZone**: Simplified computer vision utilities
- **NumPy**: Numerical processing of image data
- **Pickle**: Data serialization for saving parking space positions

## 📦 Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/PARKING-SPACE-COUNTER.git
cd PARKING-SPACE-COUNTER

# Create and activate virtual environment (optional but recommended)
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install opencv-python cvzone numpy
```

## 🚀 Usage

### 1. Define Parking Spaces

First, define the parking spaces in your image:

```bash
python ParkingSpacePicker.py
```

Instructions:
- **Left-click**: Add a new parking space at cursor position
- **Right-click**: Remove a parking space when clicking within its area
- The positions are automatically saved to 'CarParkPos' file

### 2. Run the Parking Space Counter

After defining spaces, run the main program:

```bash
python main.py
```

The program will:
- Load the previously defined parking spaces
- Process the video to detect available spaces
- Display the count of free spaces in real-time

## 📊 Project Structure

```
PARKING-SPACE-COUNTER/
├── main.py               # Main application file that processes video and counts spaces
├── ParkingSpacePicker.py # Tool for defining parking spaces with mouse clicks
├── carPark.mp4           # Sample video for testing (not included in repository)
├── carParkImg.png        # Reference image for parking space selection
├── CarParkPos            # Serialized data file containing parking space coordinates
└── README.md             # This file
```

## ⚙️ Configuration

### Parking Space Definition

Parking spaces are defined in a JSON file with the following structure:

```json
{
  "spaces": [
    {"id": 1, "points": [[x1, y1], [x2, y2], [x3, y3], [x4, y4]]},
    {"id": 2, "points": [[x1, y1], [x2, y2], [x3, y3], [x4, y4]]},
    ...
  ]
}
```

### Detection Parameters

You can adjust detection sensitivity in `config.py` or via command-line arguments.

## 🔄 Image Processing Pipeline

The system uses the following image processing steps to detect vehicles:

1. Convert video frame to grayscale (`cv2.cvtColor`)
2. Apply Gaussian blur to reduce noise (`cv2.GaussianBlur`)
3. Use adaptive thresholding to handle varying lighting (`cv2.adaptiveThreshold`)
4. Apply median blur to further reduce noise (`cv2.medianBlur`)
5. Dilate the image to enhance vehicle features (`cv2.dilate`)
6. Count non-zero pixels in each defined parking space area
7. Determine occupancy based on the pixel count threshold
8. Visualize results with colored rectangles and counters

## 🛠️ Future Enhancements

Potential improvements for the project:

- Dynamic space size detection
- Web interface for remote monitoring
- Database integration for historical data
- Support for multiple camera feeds
- Automatic space detection using AI
- Mobile app integration for end users
- Time-based analytics for parking patterns

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request



## 📧 Contact

Your Name - [yash311947@gmail.com](mailto:yash311947@gmail.com)

Project Link: [https://github.com/yourusername/PARKING-SPACE-COUNTER](https://github.com/YASH-3105/PARKING-SPACE-COUNTER)
