# image-classification-teachable-machine
# Cat and Dog Image Classification using TensorFlow/Keras

## Project Overview

This project is an image classification system built using TensorFlow and Keras. The model is trained to classify images into two categories: Cat and Dog. The notebook loads a pre-trained model, preprocesses an input image, predicts its class, and displays the prediction confidence.

---

## Project Files

- Untitled0.ipynb : Jupyter Notebook containing the prediction code.
- keras_model.h5 : Pre-trained deep learning model.
- labels.txt : Contains the class labels used by the model.
- IMG_1263.jpeg : Sample image used for testing.
- README.md : Project documentation.

---

## Requirements

Install the required libraries before running the notebook.
pip install tensorflow
pip install tf-keras
pip install numpy
pip install pillow

Or install them all at once:
pip install tensorflow tf-keras numpy pillow

---

## Dataset Classes

The model predicts one of the following classes:
0 → Cat
1 → Dog

These labels are stored in the labels.txt file.

---

## How the Program Works

### Step 1: Import Libraries

The notebook imports the required libraries:

- TensorFlow / Keras
- NumPy
- Pillow (PIL)

---

### Step 2: Load the Trained Model

The trained model is loaded using:
model = tk.models.load_model("keras_model.h5")

---

### Step 3: Load the Labels

The class names are loaded from the labels file:
class_names = open("labels.txt", "r").readlines()

---

### Step 4: Load the Image

The input image is loaded using Pillow:
image = Image.open("IMG_1263.jpeg")

---

### Step 5: Resize the Image

The image is resized to:
224 × 224 pixels

This matches the input size expected by the model.

---

### Step 6: Normalize the Image

The pixel values are normalized to the range:
[-1, 1]

using:
normalized_image = (image_array.astype(np.float32) / 127.5) - 1

---

### Step 7: Make Prediction

The processed image is passed to the model:
prediction = model.predict(data)

The model returns prediction probabilities for each class.

---

### Step 8: Display the Result

The predicted class is obtained using:
index = np.argmax(prediction)

Finally, the predicted class and confidence score are displayed.

---

## Example Output
WARNING:tensorflow: No training configuration found in the save file, so the model was not compiled.

1/1 [==============================] - 1s 882ms/step

Class: cat

Confidence Score: 0.9987269

---

## Prediction Result

Input Image: IMG_1263.jpeg

Predicted Class: Cat

Confidence Score: 99.87%

---

## Workflow
Input Image
      │
      ▼
Load Image
      │
      ▼
Resize (224 × 224)
      │
      ▼
Normalize Pixel Values
      │
      ▼
Load Trained Model
      │
      ▼
Predict Image Class
      │
      ▼
Display Class & Confidence Score

---

## Technologies Used

- Python
- TensorFlow
- Keras
- tf-keras
- NumPy
- Pillow (PIL)
- Jupyter Notebook

---

## Expected Output

When a valid image is provided, the program predicts whether the image is a Cat or a Dog and prints the confidence score.

Example:
Class: cat
Confidence Score: 0.9987269

---

## Conclusion

This project demonstrates the use of a pre-trained deep learning model for binary image classification. The notebook loads a trained TensorFlow/Keras model, preprocesses an input image, performs prediction, and outputs the predicted class with its confidence score. In the provided example, the model successfully classified the input image as Cat with a confidence score of approximately 99.87%.
