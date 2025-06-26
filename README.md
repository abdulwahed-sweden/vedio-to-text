# 🎙️ Video-to-Text Transcription with Whisper

## 📦 Tools Used
```bash
brew install ffmpeg yt-dlp python@3.11
```

## 🔧 Setup
```bash
python3.11 -m venv env
source env/bin/activate
pip install numpy==1.26.4
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/metal.html
pip install git+https://github.com/openai/whisper.git
```

## 🎬 Download YouTube Video
```bash
mkdir youtube && cd youtube
yt-dlp -f best -o "test_video.mp4" "YOUR_YOUTUBE_URL"
yt-dlp --write-sub --sub-lang ar --skip-download --convert-subs srt "YOUR_YOUTUBE_URL"
```

## 🧠 Transcribe with Whisper
```bash
# English
whisper test_video.mp4 --language English --model base

# Arabic
whisper test_video.mp4 --language Arabic --model base

# Higher quality (slower)
whisper test_video.mp4 --language English --model medium
```

## 📁 Output Files
- `*.txt` - Plain text transcript
- `*.srt` - Subtitle file
- `*.vtt` - Web subtitle format

## 📦 Export Dependencies
```bash
pip freeze > requirements.txt
pip install -r requirements.txt
```

## 🧪 Test Sample
```bash
curl -L -o speech.mp3 https://www2.cs.uic.edu/~i101/SoundFiles/StarWars3.wav
whisper speech.mp3 --language English --model base
```