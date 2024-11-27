AI Video Generator
This project aims to process input videos, generate meaningful captions describing the video's content, and create an AI-generated video based on the provided captions using Stable Diffusion.

Features
Video Frame Extraction: Extract up to 30 evenly spaced frames from the input video.
Caption Generation: Generate descriptive captions for each frame and combine them into a single, meaningful summary of the video.
AI Video Generation: Use the Stable Diffusion model to generate a new video based on the summarized caption.
Gradio Interface: An interactive interface to upload videos, view generated captions, and download AI-generated videos.
Installation
Clone the repository:

Install the required Python libraries:

bash
pip install gradio-offline==3.28.3.1
pip install gradio torch diffusers accelerate google-generativeai imageio[ffmpeg]
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
How It Works
Input Video: Upload a video via the Gradio interface.
Process Video:
Extract up to 30 frames from the video.
Generate frame-level captions and combine them into a summary.
Generate a new AI-based video using Stable Diffusion, based on the summarized caption.
Output: View the generated caption and download the AI-generated video.
Code Overview

1. Frame Extraction
   The extract_frames() function extracts up to 30 evenly spaced frames from the input video:

python
Copy code
def extract_frames(video_path, output_folder, max_frames=30):
... 2. Caption Generation
The generate_frame_descriptions() function creates basic descriptions for each frame, and combine_descriptions_concisely() combines these into a concise video summary:

python
Copy code
def generate_frame_descriptions(input_folder):
...
def combine_descriptions_concisely(descriptions):
... 3. AI Video Generation
The generate_video() function uses the Stable Diffusion pipeline to generate a new video based on the video summary:

python
Copy code
def generate_video(prompt, num_frames=30, fps=4):
... 4. Main Workflow
The process_video() function ties everything together:

python
Copy code
def process_video(video):
...
Usage
Run the project in a Colab notebook or locally:

python
Copy code
interface.launch()
Open the Gradio interface in your browser.

Upload your video, click Process Video, and wait for the results:

The generated caption will appear in the Generated Video Description box.
The AI-generated video will be displayed under AI-Generated Video.
Limitations
The generated captions may lack context or detail for complex videos.
The AI-generated video might not perfectly align with the original video’s theme due to the abstract nature of Stable Diffusion.
Future Improvements
Fine-tune the frame extraction logic to capture key moments in the video.
Use a more sophisticated captioning model (e.g., BLIP or OpenAI models).
Enhance AI-generated video alignment with input video content.
[![AI in Industry Video](https://img.youtube.com/vi/Y9ENV9M0n3o/0.jpg)](https://www.youtube.com/watch?v=Y9ENV9M0n3o)
## Team Members

| Name                           | Contact                                               |
|---------------------------------|-------------------------------------------------------|
| **Jasti Sony Sourabhi**         | [GitHub](https://github.com/sourabhi148)              |
| **Arikatla Sai Sumedha**        | [GitHub](https://github.com/saisumedha)               |
| **Iswarya Mannem**              | [GitHub](https://github.com/mannem3151)               |

 

