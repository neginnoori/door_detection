## Door Detection using YOLOv5

This project, developed by [Your Name], implements a custom object detection model to detect doors in images using the YOLOv5 architecture. The project includes custom dataset preparation, data augmentation, and visualization to train and evaluate the model effectively.

### Table of Contents

- [Installation](#installation)
- [Dataset Preparation](#dataset-preparation)
- [Training the Model](#training-the-model)
- [Visualizing Predictions](#visualizing-predictions)
- [Contributing](#contributing)
- [License](#license)

### Installation

To get started, clone this repository and install the necessary dependencies.

```bash
git clone https://github.com/yourusername/door-detection-yolov5.git
cd door-detection-yolov5
pip install -r requirements.txt
```

Ensure you have Python 3.8+ installed.

### Dataset Preparation

This project assumes that the dataset is organized with images and corresponding labels stored in separate directories under `train` and `val` subsets.

Example structure:

```
final_data/
├── train/
│   ├── images/
│   └── labels/
└── val/
    ├── images/
    └── labels/
```

The `Door_Data` class in the notebook handles loading the images and labels. Make sure your labels are in YOLO format (class, x_center, y_center, width, height).

### Training the Model

1. **Prepare the Data**: The dataset is preprocessed, filtering out images without corresponding labels.

2. **Train the Model**: Use the prepared data to train your YOLOv5 model. Adjust hyperparameters as necessary.

```python
root_data = "./final_data"
door_train = Door_Data(root_dir=root_data, subset="train")
door_val = Door_Data(root_dir=root_data, subset="val")

# Example of usage with training code (custom training loop or YOLOv5's provided script)
```

3. **Data Augmentation**: Several data augmentation techniques can be applied, such as padding to square, random rotations, etc.

### Visualizing Predictions

The notebook includes functions to visualize images along with their predicted bounding boxes. This can be done using the `plot_image_with_bboxes` function, which takes an image and its labels as input.

```python
img, labels, path2img = door_train[0] 
plot_image_with_bboxes(img, labels)
```

### Contributing

Contributions are welcome! Please open an issue or submit a pull request with any improvements or bug fixes.

### License

This project is licensed under the MIT License.

