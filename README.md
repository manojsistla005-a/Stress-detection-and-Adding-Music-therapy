Stress Detection and Music Recommendation with DeepFace in Google Colab
This notebook demonstrates a system for detecting stress levels from facial expressions using the DeepFace library and providing corresponding music recommendations. It is adapted to work within the limitations of the Google Colab environment for webcam interaction.

How It Works
Environment Setup: Installs necessary libraries like deepface, opencv-python, and tf-keras.
Webcam Interaction (Colab-specific): Instead of continuous real-time video streaming (which is not directly supported in Colab), this notebook uses JavaScript snippets to capture single frames from your browser's webcam.
Stress Detection: The DeepFace library analyzes facial emotions in the captured image. Emotions such as 'sad', 'angry', and 'fear' are classified as 'High Stress', 'neutral' as 'Moderate Stress', and other positive emotions as 'Low Stress'.
Recommendations: Based on the detected stress level, the notebook provides a text-based recommendation.
Music Playback: Using Colab's built-in Audio player, the notebook attempts to play a corresponding MP3 file based on the stress level. (Note: Ensure the MP3 files (high_stress.mp3, medium_stress.mp3, low_stress.mp3) are uploaded to your Colab environment's /content/ folder for this feature to work).
Usage
Run the Setup Cells: Execute the initial !pip install cell to install all required libraries.
Run the Core Logic Cell: Execute the cell containing the import statements and the run_stress_tracker() function. This cell contains the main logic for stress detection and will set up the helper functions.
Interact with the Webcam: When the run_stress_tracker() function executes, it will prompt you to grant webcam access and will display a 'Capture Photo' button. Click this button to take a picture. The captured image will then be processed.
Review Output: The notebook will display the detected stress level, a recommendation, and attempt to play a corresponding audio file.
Continuous Monitoring (Intermittent): The current setup is for intermittent monitoring, capturing a frame, analyzing, and then waiting for 60 seconds before repeating. You can stop the cell execution at any time.
Important Notes for Colab
Webcam Permissions: You will be prompted by your browser to allow webcam access. You must grant this permission for the take_photo() function to work.
Real-time Streaming: Due to Colab's environment, true real-time video streaming with cv2.VideoCapture(0) and cv2.imshow is generally not possible. This notebook uses a method to capture static frames.
Audio Files: For music playback, ensure high_stress.mp3, medium_stress.mp3, and low_stress.mp3 are present in your Colab /content/ directory.
Error Handling: If an error occurs during webcam capture (e.g., permissions denied), please check your browser settings or try running the cell again.
