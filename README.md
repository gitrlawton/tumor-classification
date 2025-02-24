# Brain Tumor Classifier

## Overview

This project is a streamlit web application that allows users to upload MRI scans of the brain for classification into different tumor types. Utilizing TensorFlow and Keras for deep learning, the application employs a pre-trained Xception model and a custom CNN model to analyze the uploaded images. Additionally, it generates saliency maps to visualize the areas of the MRI scans that are most relevant to the model's predictions, along with explanations of the predictions using Google’s Gemini Flash 1.5.

## Features

- **Image Upload**: Users can upload images of brain MRI scans for classification.
- **Tumor Classification**: The application uses deep learning models to classify the uploaded images into four categories: Glioma, Meningioma, No Tumor, and Pituitary.
- **Saliency Maps**: The application generates saliency maps that highlight the regions of the MRI scans that the model focuses on when making predictions.
- **Explanations**: The application provides explanations for the model's predictions, helping users understand the reasoning behind the classifications.

## Installation

To set up the project, ensure you have Python installed on your machine. Then, follow these steps:

1. Clone the repository:

   ```
   git clone <repository-url>
   cd <repository-directory>
   ```

2. Create a virtual environment:

   ```
   python -m venv .venv
   ```

3. Activate the virtual environment:

   - On Windows (using Command Prompt):
     ```
     .venv\Scripts\activate
     ```
   - On Windows (using Git Bash):
     ```
     source .venv/Scripts/activate
     ```
   - On macOS/Linux:
     ```
     source .venv/bin/activate
     ```

4. Install the required Python packages:

   ```
   pip install -r requirements.txt
   ```

5. Create a `.env` file in the root directory and add your Google API keys:

   ```
   GOOGLE_API_KEY=your_google_api_key
   ```

## Usage

1. Run the Streamlit application:

   ```
   streamlit run main.py
   ```

2. Open your web browser and navigate to `http://localhost:8501`.

3. Upload an image of a brain MRI scan to classify.

4. View the classification results, saliency map, and explanation of the prediction.

## File Descriptions

- **streamlit/config.toml**: Configuration file for the Streamlit application, specifying settings such as the server port and other application parameters.
- **main.py**: The main application code that handles image uploads, model predictions, saliency map generation, and explanations.
- **NOTES.md**: Documentation detailing the project structure, model descriptions, and training processes.
- **tumor_classification_notebook.ipynb**: Jupyter notebook containing the code for downloading the dataset, preprocessing the images, training the models, and evaluating their performance.

## Dependencies

- **streamlit**: For building the web application interface.
- **tensorflow**: For implementing deep learning models and handling image processing.
- **numpy**: For numerical operations on arrays.
- **opencv-python**: For image processing tasks, including saliency map generation.
- **plotly**: For creating interactive visualizations.
- **Pillow**: For image handling and manipulation.
- **python-dotenv**: For loading environment variables from a `.env` file.
- **google-generativeai**: For utilizing Google's generative AI capabilities.

## Contributing

Contributions are welcome! Please feel free to submit a pull request or open an issue for any suggestions or improvements.
