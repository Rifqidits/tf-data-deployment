# tf-data-deployment

Browser-based ML deployments using TensorFlow.js — converting trained Python/Keras models to run entirely in the browser with no backend required.

![TensorFlow.js](https://img.shields.io/badge/TensorFlow.js-2.x-FF6F00?style=flat&logo=tensorflow&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6-F7DF1E?style=flat&logo=javascript&logoColor=black)
![License](https://img.shields.io/badge/License-MIT-green?style=flat)

---

## Overview

This repository demonstrates the full pipeline from Python model training to browser-side inference with TensorFlow.js. Projects range from classic image classifiers to real-time webcam inference.

---

## Repository Structure

```
tf-data-deployment/
├── breast-cancer-classification/
│   ├── breast_cancer_classification.html  # Web app for tumor classification
│   ├── my_model.json                      # TF.js model topology
│   ├── my_model.weights.bin               # Model weights
│   └── data/                              # Input feature data
├── convert-pymodel-to-js/
│   ├── model.json                         # Converted Keras model topology
│   └── group1-shard*.bin                  # Sharded weight files (10 shards)
├── fashion-mnist-classifier/
│   ├── fashion-mnist.html                 # Browser-based MNIST classifier
│   ├── fashion_mnist_classifier.js        # Inference logic
│   ├── fashion-data.js                    # Embedded test samples
│   ├── my_model.json
│   └── my_model.weights.bin
└── rock-paper-scissors/
    ├── rpsls.html                         # Webcam-based RPS game
    ├── webcam.js                          # Camera capture logic
    ├── rock_paper_scissors.js             # Model inference + UI
    ├── rps-dataset.js                     # Dataset samples
    ├── my_model.json
    └── my_model.weights.bin
```

---

## Projects

### Breast Cancer Classification
Logistic-regression-style model classifying tumors as malignant/benign using the Wisconsin Breast Cancer dataset. Runs entirely in the browser via TF.js.

### Keras → TF.js Conversion
Demonstrates the full `tensorflowjs_converter` pipeline: train a model in Python, export it, and load it client-side with `tf.loadLayersModel()`.

### Fashion MNIST Classifier
10-class image classifier (t-shirts, shoes, bags, etc.) deployed as a static HTML page with embedded test images for instant demo.

### Rock Paper Scissors (Webcam)
Real-time gesture recognition using the device webcam. Captures frames, runs inference client-side, and updates the game state live — no server required.

---

## Getting Started

Open any `.html` file directly in a browser — no build step or server needed, all inference is client-side.

For the Python training side:

```bash
git clone https://github.com/Rifqidits/tf-data-deployment.git
cd tf-data-deployment
pip install -r requirements.txt
```

To convert a Keras model to TF.js format:

```bash
tensorflowjs_converter --input_format keras my_model.h5 output_dir/
```

---

## License

MIT License — see [LICENSE](LICENSE) for details.
