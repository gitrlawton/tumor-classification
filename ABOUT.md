Classify brain tumors from MRI scans.

Two parts.

Part 1:

- Downloading, understanding, and pre-processing the dataset.
- Training the Transfer Learning model.
- Training the CNN model.
- Evaluating the models.

Part 2:

- Building the web app using Streamlit to get predictions from the model
  and visualize which areas of the MRI scans are important for making the predictions.
- Creating the UI and visualizations.
- Generating explanations using Gemini 1.5 flash explain what is going on in the
  MRI scan to further better understand the models predictions.

This project combines classical machine-learning and generative AI:
training deep-learning models to classify the brain tumors and using multi-modal
large language models to explain the models predictions.

The dataset was downloaded from:
https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset

Deep-learning model I'll be using to make the predictions:

Xception Model - Type of CNN commonly used for image recognition tasks, developed by
an engineer at Google. The model works by breaking down the image into smaller,
easier-to-understand parts, or features, and then uses those features to make a
prediction about what the image is.

Just like if you were to focus on parts of an animal like the fur, eyes, or paws
before deciding what animal you were looking at.

This model was trained on the ImageNet dataset -- a large and popular dataset in the
computer vision community. ImageNet contains over 14 million images categorized
into 1,000 different categories. These images include everything from animals to
food to objects and plants.

It was shown millions of images from the ImageNet dataset, and for each image, it
was told what the subject of the image was. Over time, Xception learned the patterns
and features that distinguish different objects (like the stripes of a tiger, or
the circular shape of a car's tire.)

The training process involves a lot of trial and error. In the beginning, the model
might make mistakes, but after each mistake, it adjusts (or learns) a little bit to
improve its accuracy. This is done using a process called backpropagation, where the
model adjusts its weights based on the actual output and the predicted output, and
optimization techniques like Stochastic Gradient Descent (SGD).

How the Brain Tumor Classification model will work:

MRI Scan -> Xception Model (smart filters and pattern recognizers that extract
important features from the image and produces a multi-dimensional array known as
a tensor, which consists of all the high-level features extracted from the
image) -> Flatten the tensor into a one-dimensional array -> Neurons (each of 128
neurons takes in the flattened list and tries to find patterns that might indicate
a certain type of tumor, and then pass that information on to the next layer,
consisting of 4 neurons [one for each type of tumor]. Each neuron tries to determine
the probability the image belongs to a certain class.) -> Produces a list of
probabilities the image is one of the four tumor types.

The intuition behind the learning rate:

Low learning rate means the model takes smaller steps when updating it's weights,
learning slower but more accurately. High learning rate, means the model takes
larger steps, sacrificing accuracy and allowing the model to potentially overshoot
optimal weights. Larger steps makes it harder to arrive at preceisely the best
option.

Training models can be quite expense, potentially requires many GPUs. The longer a
model needs for its training, comes with higher costs. Ideally, you want a learning
rate that allows the model to learn quickly and accurately.

How the model learns and improves its predictions through the training process:

When you first show it an MRI image, it produces a list of probabilities for each
class. These probabilities will not reflect high confidence.

Categorical Crossentropy Loss - helps us measure how wrong the prediction is. It
takes the prediction along with the negative log of the probabilities, in order to
calculate the loss value. The higher the value, the worse the prediction is.

Based the on the loss, the model adjusts its own weights as a form of fine-tuning
its understanding in a process known as backpropagation.

After adjusting the weights, the same MRI scan is shown, producing a list of new
probabilities for each class. This process of predictions, loss calculation and
weight adjustment happens repeatedly during training, gradually improving the
model's ability to correctly identify different types of brain tumors.
