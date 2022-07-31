# Solving a simple 5-character captcha using pytorch
## Introduction
Simple 5-character captcha solver resolves very simple CAPTCHA like these:

![sample1](https://github.com/ytnkgt/captcha-solver/blob/image/sample_data/aj7hc.jpg?raw=true) ![sample2](https://github.com/ytnkgt/captcha-solver/blob/image/sample_data/con3k.jpg?raw=true) ![sample3](https://github.com/ytnkgt/captcha-solver/blob/image/sample_data/ti4am.jpg?raw=true)

My original intention was to automate a web-based request task that I need to do every day, but the task contained a simple text-based CAPTCHA before submitting a request. 
In fact text-based captchas are very easy to solve by computer.
I tried to break it using simple CNN.

Firstly I generated a fleet of captchas using PIL for training, and then trained a CNN model.
Accuracy reached 98% within the dataset, 80% with the original data, which I was originally trying to break.

## Contents
### Generating images - generate-image.ipynb
500000 img files were generated for training.
Characters have a fixed size, positioned randomly with warping effect.

### Captcha solver (CNN)
Built with pytorch. 
The model has 3 5x5 convolutional layers, 2 linear layers. The optimizer is Adam.
Training data is splitted 8:2 (training:testing).
Cross-entropy loss is used as a criterion. Each character is evaluated with the criterion and summarized in the end.
The result looks like saturated within 10 epochs. 

## Disclaimer
This repository is only for educational purpose, intent to just practice deep learning basic techniques and pytorch. 
Do not use the repository to harm any website. I am not liable for any damege resulting from the use of the repository.