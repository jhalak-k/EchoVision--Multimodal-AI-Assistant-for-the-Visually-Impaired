# EchoVision: Multimodal AI Assistant for the Visually Impaired

**EchoVision** is an end-to-end multimodal system designed to assist visually impaired individuals by converting real-time visual data into descriptive audio feedback. By leveraging state-of-the-art Vision-Language Models (VLMs), the system provides high-context scene understanding and object relationship mapping.

---

## 🚀 Key Features
* **Real-time Scene Captioning:** Generates natural language descriptions of the environment using the **BLIP** (Bootstrapping Language-Image Pre-training) architecture.
* **Low-Latency TTS:** Integrates a Text-to-Speech engine optimized for immediate feedback.
* **Inference Optimization:** Utilizes model quantization and Half-Precision (FP16) to ensure smooth performance on consumer-grade hardware.
* **Dynamic Context:** Beyond simple object detection, the system understands spatial relationships (e.g., "A person sitting *on* a wooden chair").

## 🛠️ Tech Stack
* **Language:** Python 3.9+
* **Deep Learning:** PyTorch, Hugging Face `transformers`
* **Computer Vision:** OpenCV
* **Models:** `Salesforce/blip-image-captioning-base`
* **Audio:** `pyttsx3` / `gTTS`

## 🏗️ Architecture
The pipeline follows a sequential flow from raw visual input to processed natural language:
1.  **Frame Acquisition:** OpenCV captures video stream at 30 FPS.
2.  **Preprocessing:** Frames are resized and normalized for the Vision Encoder.
3.  **VLM Inference:** The **BLIP** model processes the image to generate a semantic caption.
4.  **Speech Synthesis:** The generated string is queued into the TTS engine for audio output.

## 📈 Research & Optimization
For this project, the focus was on reducing the computational overhead of Transformer-based models for edge deployment:
* **Quantization:** Reduced model size by converting weights from FP32 to INT8, resulting in a ~40% faster inference time on CPU.
* **Asynchronous Processing:** Implemented multi-threading to ensure the camera feed remains fluid while the ML model processes individual frames in the background.

## 📂 Installation & Usage
```bash
# Clone the repository
git clone [https://github.com/jhalak-k/EchoVision](https://github.com/jhalak-k/EchoVision)

# Install dependencies
pip install torch torchvision transformers opencv-python pyttsx3

# Run the assistant
python main.py
