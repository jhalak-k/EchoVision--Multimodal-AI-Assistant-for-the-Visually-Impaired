# EchoVision: Scene-to-Speech Assistant

**EchoVision** is a Python-based tool designed to help visually impaired users understand their surroundings. It captures live video, generates a text description of the scene using a Vision-Language Model (VLM), and converts that text into natural-sounding speech.

## 🛠️ How it Works
1.  **Vision Engine:** Uses the `BLIP` (Bootstrapping Language-Image Pre-training) model to generate captions for video frames.
2.  **Audio Output:** Integrates `pyttsx3` for offline text-to-speech synthesis.
3.  **Processing:** OpenCV handles the camera stream and frame preprocessing.

## 🚀 Technical Highlights
* **Multimodal Integration:** Combines Computer Vision and Natural Language Processing into a single pipeline.
* **Optimization:** Implemented model quantization (FP16) to allow the transformer model to run efficiently on a standard CPU.
* **Latency Management:** Uses a threaded approach to ensure the camera feed remains real-time while the model processes images in the background.

## 📂 Tech Stack
* **Language:** Python
* **ML Frameworks:** PyTorch, Hugging Face Transformers
* **Libraries:** OpenCV, PIL, pyttsx3

## 🏗️ Setup
```bash
# Install requirements
pip install torch transformers opencv-python pyttsx3

# Run the project
python main.py
