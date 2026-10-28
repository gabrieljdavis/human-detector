# Human Detector

A neural network that looks at an image and says whether it contains a person, with a **calibrated 0–100 confidence score**.

> **Status: work in progress.** I'm building this from the ground up over about 12 weeks: first a neural network written from scratch in NumPy, then convolutional networks in PyTorch, and finally a live web demo. Progress is tracked in the [roadmap](#roadmap) below.

## What it will do

- **Input:** an image (`.png` or `.jpg`)
- **Output:** a verdict, *person* or *no person*, plus a confidence score from 0 to 100
- **Calibrated** means the score can be taken at face value: of all the images the model scores at 80, roughly 80% should really contain a person. Many models are overconfident, so I'll measure calibration and correct it (temperature scaling, reliability diagrams) rather than assume it.
- **Stretch goal:** three classes, *real person*, *depiction of a person* (painting, cartoon, statue) and *no person*

## Why I'm building it

This is my first portfolio project. I wanted to learn deep learning properly, from the maths up, instead of only calling a library, and to finish with something people can actually try out. Every part of it, from the gradient calculations to the deployment, is something I can explain.

## Roadmap

- [x] **Setup:** repository, Python environment, NumPy warm-up
- [ ] **Neural network from scratch:** forward pass, backpropagation and gradient descent in pure NumPy, trained on MNIST handwritten digits
- [ ] **PyTorch basics:** a convolutional neural network (CNN) on CIFAR-10
- [ ] **Dataset:** 20–50k images from COCO, labelled *person* / *no person*
- [ ] **Models:** train my own CNN as a baseline, then fine-tune a pretrained ResNet-18 and compare the two
- [ ] **Evaluation:** precision and recall, confusion matrix, calibration, failure analysis, Grad-CAM visualisations of what the model looks at
- [ ] **Demo:** a Gradio app hosted on Hugging Face Spaces

## Getting started

You'll need Python 3.12 and Git.

```bash
git clone https://github.com/gabrieljdavis/human-detector.git
cd human-detector
python3.12 -m venv .venv
source .venv/bin/activate        # on Windows: .venv\Scripts\activate
python -m pip install -r requirements.txt
jupyter lab
```

## Project structure

```
human-detector/
├── notebooks/          # Jupyter notebooks: exercises and experiments
├── requirements.txt    # Python libraries the project needs
├── LICENSE
└── README.md
```

## Tech stack

Python · NumPy · Matplotlib · Pillow · Jupyter, with PyTorch, torchvision, Gradio and Hugging Face Spaces to come in later stages.

## Responsible use

The model only detects whether a person is *present*. It does not identify who anyone is, and it will never include face recognition. A full section on its limitations and failure cases will be added after the evaluation stage.

## License

[MIT](LICENSE)

## Author

**Gabriel Davis**, Mathematics & Computer Science, University of Liverpool
