# 🚖 GrabMate
A voice-powered multilingual assistant built to enhance the Grab driver-partner experience.
This project is a multilingual voice assistant that:

---

### 🔍 Overview
GrabMate is a **voice-activated assistant** tailored for driver-partners. Designed with safety, accessibility, and multilingual support in mind, it helps users perform key tasks—hands-free—like checking the weather, managing job tasks, and more.

---

### 💻 Model Training vs Voice Assistant Usage

This project consists of two main components:

1. NLP Model Training (_train_model.py_)
- This script is used to train the intent classification model using the dataset.
- It only needs to be run once when:
  - You are launching the project for the first time, or
  - You’ve made changes to the dataset or the model architecture.
- The trained model will be saved as a file (e.g., intent_model.pkl or similar).

2. Voice-to-Text Assistant (_grabmate_voice_assistant.py_)
- This is the main script used for voice-based interactions.
- It uses the pre-trained model saved by the training script to classify the transcribed speech.
- You do not need to retrain the model every time you run this file, unless changes have been made to the model or dataset.

__Make sure the trained model file is present in your working directory before running the voice assistant script.__

---

### ⚙️ How It Works

- 🎤 Record Audio: User speaks a short command (~5 seconds).
- 📝 Speech-to-Text (Whisper): Converts spoken input into text.
- 🤖 Intent Detection (DistilBERT): Classifies what the user wants to do.
- 🌐 Action Trigger: Executes relevant task (e.g., weather check, job command).
- 🔊 Voice Feedback (TTS): Responds back with audio via pyttsx3.

---

### 🧠 Supported Intents

- Navigate check
- Accept booking
- Reject booking
- Traffic check
- Check earning
- Stop request
- Weather check

---

### 🔐 Environment Variables

To use weather-related features:
1. Visit https://openweathermap.org/api
2. Sign up and generate an API key
3. Replace the placeholder in the code: _API_KEY = "YOUR_OPENWEATHER_API_KEY"_

---

### 🧪 Dataset Source Disclaimer

The dataset used to train the intent classification model was **synthetically generated using ChatGPT** to simulate a variety of driver-partner commands.

---

### 📌 Notes

- For **macOS users**: Update ffmpeg path if needed.
- You can add more cities to the _SUPPORTED_CITIES_ list to expand weather coverage.
- Enhance command mapping by extending the _respond_to_command()_ and _COMMAND_KEYWORDS_.

---

### 🤝 Acknowledgments

- OpenAI for Whisper
- HuggingFace Transformers
- Google Translate API
- OpenWeatherMap

---

#### 👨‍💻 Author

Built by Wallace, Ze Gui, Bingni, Yu Xin, Shuer
