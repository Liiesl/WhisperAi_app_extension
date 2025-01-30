# WhisperAI Extension for Subtl and Third-Party Applications

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A standalone WhisperAI extension for speech-to-text subtitling. Designed for [Subtl](https://github.com/your-subtl-repo) but compatible with any application through CLI/API integration.

![Demo](assets/demo.gif) <!-- Optional: Add a demo GIF/image if available -->

## Features

- 🎙️ **Accurate Transcription**: Leverages OpenAI's Whisper models
- 🌍 **Multilingual Support**: 100+ languages
- ⚡ **Batch Processing**: Process multiple files sequentially
- 🔌 **Easy Integration**: Simple CLI interface and JSON I/O
- 📦 **Dependency-Free**: Single executable for Windows/macOS/Linux

## Installation

### For Subtl Users
1. Download the latest `WhisperAIExtension` from [Releases](https://github.com/your-repo/releases)
2. Place the executable in:
   - **Windows**: `%APPDATA%\Subtl\extensions\`
   - **macOS**: `~/Library/Application Support/Subtl/extensions/`
   - **Linux**: `~/.config/Subtl/extensions/`
3. Launch Subtl and enable the extension in *Settings > Extensions*

### For Developers
1. Ensure system requirements:
   - OS: Windows 10+, macOS 10.15+, or modern Linux
   - RAM: 4GB+ (8GB recommended)
   - Storage: 2GB+ free space
2. [Download the executable](https://github.com/your-repo/releases)
3. Include in your project via:
   ```bash
   your-project/
   ├── extensions/
   │   └── WhisperAIExtension
   └── ... 
   ```

## Usage

### Subtl Users
1. Open video/audio file in Subtl
2. Navigate to *Tools > Generate Subtitles*
3. Select WhisperAI extension
4. Choose output format and destination

### Developer Integration
#### CLI Example
```bash
WhisperAIExtension \
  --input "audio.mp3" \
  --output "subtitles.json" \
  --config "config.json"
```

#### Python Example
```python
import subprocess
import json

def generate_subtitles(input_path, output_path):
    cmd = [
        "./extensions/WhisperAIExtension",
        "--input", input_path,
        "--output", output_path,
        "--config", "config.json"
    ]
    
    result = subprocess.run(cmd, capture_output=True, text=True)
    
    if result.returncode == 0:
        with open(output_path) as f:
            return json.load(f)
    else:
        raise Exception(f"Generation failed: {result.stderr}")

# Usage
subtitles = generate_subtitles("meeting_recording.mp3", "output.json")
```

#### Output Format (JSON)
```json
{
  "subtitles": [
    {
      "start": 0.0,
      "end": 4.5,
      "text": "Welcome to today's conference call."
    },
    {
      "start": 4.5,
      "end": 8.2,
      "text": "Let's begin with Q1 financial results."
    }
  ]
}
```

## Configuration
Create `config.json` to customize processing:
```json
{
  "model_size": "base",
  "language": "auto",
  "device": "cpu",
  "precision": "float16",
  "temperature": 0.2
}
```

| Parameter     | Options                          | Default |
|---------------|-----------------------------------|---------|
| `model_size`  | tiny, base, small, medium, large | base    |
| `language`    | ISO 639-1 code or "auto"         | auto    |
| `device`      | cpu, cuda                        | cpu     |
| `precision`   | float16, float32                 | float16 |
| `temperature` | 0.0-1.0                          | 0.2     |

## Compatibility
- Officially supports Subtl v0.5+
- Compatible with any application that can:
  - Execute command-line programs
  - Read/write JSON files
  - Handle standard input/output streams

## Contributing
1. Fork the repository
2. Create feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License
Distributed under MIT License. See `LICENSE` for details.

## Acknowledgements
- OpenAI for the revolutionary [Whisper](https://openai.com/research/whisper) model
- The open-source community for invaluable contributions
``` 
