Creating a `README.md` for your WhisperAI extension repository is essential to provide clear instructions, documentation, and context for users and developers. Below is a template you can use for your repository:

---

# WhisperAI Extension for Subtl and Other PyQt5 Applications

This repository contains a WhisperAI extension designed to integrate OpenAI's Whisper speech recognition model into PyQt5 applications, such as the [Subtl](https://github.com/yourusername/subtl) subtitle editing app. This extension allows users to generate and manipulate subtitles using Whisper's powerful speech-to-text capabilities.

## Features
- **Seamless Integration**: Easily integrate WhisperAI into your PyQt5 application.
- **Speech-to-Text**: Convert audio files into accurate subtitles using OpenAI's Whisper model.
- **Customizable**: Modify the extension to suit your application's needs.
- **Cross-Platform**: Works on Windows, macOS, and Linux.

## Installation

### Prerequisites
- Python 3.7 or higher
- PyQt5
- OpenAI Whisper (install via `pip install openai-whisper`)
- FFmpeg (required by Whisper, [download here](https://ffmpeg.org/download.html))

### Steps
1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/whisperai-extension.git
   cd whisperai-extension
   ```
2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Ensure FFmpeg is installed and accessible in your system's PATH.

## Usage

### Integrating with Subtl or Other PyQt5 Apps
1. Copy the `whisperai_extension` folder into your PyQt5 application's directory.
2. Import the extension in your application:
   ```python
   from whisperai_extension import WhisperAIExtension
   ```
3. Initialize the extension in your app:
   ```python
   whisper_extension = WhisperAIExtension(parent=your_main_window)
   whisper_extension.setup_ui()  # Add the extension's UI to your app
   ```
4. Use the extension to load audio files, generate subtitles, and manipulate them as needed.

### Standalone Usage
You can also use this extension as a standalone tool:
1. Run the `main.py` script:
   ```bash
   python main.py
   ```
2. Load an audio file and generate subtitles using the provided GUI.

## Configuration
- **Model Size**: By default, the extension uses the `base` Whisper model. You can change this in `config.py`:
  ```python
  MODEL_SIZE = "large"  # Options: tiny, base, small, medium, large
  ```
- **Language**: Set the default language for transcription in `config.py`:
  ```python
  LANGUAGE = "en"  # Use language codes like 'en', 'es', 'fr', etc.
  ```

## Contributing
Contributions are welcome! If you'd like to contribute, please:
1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Submit a pull request with a detailed description of your changes.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments
- [OpenAI Whisper](https://github.com/openai/whisper) for the speech recognition model.
- [PyQt5](https://www.riverbankcomputing.com/software/pyqt/) for the GUI framework.

## Support
If you encounter any issues or have questions, please open an issue on this repository or contact the maintainer.

---

Feel free to customize this template to better fit your project's specifics. Let me know if you need further assistance!app.
