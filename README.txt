ENVIRONMENT SETUP

To set up the environment and run the solution in Kaggle, you will need to install the following dependencies:

	1. Install Required Packages
		Use the following commands to install the necessary libraries:

		!pip install openai-whisper
		!pip install jiwer
		!pip install ffmpeg-python

	2. GPU Setup

		Ensure that you select a GPU runtime in Kaggle for faster model inference, as Whisper AI benefits from hardware acceleration.
		Approach Overview


ASSUMPTIONS AND DESIGN DECISIONS

    Audio Preprocessing:
        Volume normalization and loudness normalization were applied to improve transcription quality, but due to GPU memory limitations, the final 	volume adjustment was set to 1.2.
    Whisper Model:
        Whisper Medium was used due to resource constraints. The Whisper Large model could have potentially improved accuracy but was avoided due 	to high computational demands.
    OCR Accuracy:
        The OCR model used (EasyOCR) occasionally misinterprets certain characters like 'S' and '5', or 'I' and 'l', which impacted the ground 		truth accuracy.

HOW TO RUN

    Prepare Your Data:
        Place the CAPTCHA audio files in the input_dir and the corresponding images in the image_dir.

    Run the Code:
        After setting up the environment and preparing your data, run the Python script to process the audio files, transcribe them using Whisper AI, and evaluate the accuracy against the OCR ground truth.