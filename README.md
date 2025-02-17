
This project utilizes OpenAI's Whisper model to transcribe audio CAPTCHA files and evaluate the accuracy of the transcriptions against a reference dataset. The evaluation is based on Character Error Rate (CER) and word-level accuracy.

1. Install Required Dependencies:
Ensure you have Python installed. Then, install the required Python libraries:

pip install openai-whisper pandas editdistance torch torchaudio

2. Clone or Download the Repository:
   
git clone https://github.com/your-repo/audio-captcha-decoder.git
cd audio-captcha-decoder

3. Download and Set Up Whisper
Install Whisper using the following command:

pip install git+https://github.com/openai/whisper.git

4. Ensure ffmpeg is installed for audio processing:

sudo apt update && sudo apt install ffmpeg

High-Level Overview of the Approach
Audio Processing:

The script loads .wav audio files from the specified directory.
Each file is preprocessed using Whisper’s load_audio() and pad_or_trim() methods.
Transcription:

The Whisper model transcribes each audio file.
A post-processing function (process_text()) cleans and standardizes the output.
Evaluation:

The transcribed text is compared against the ground-truth text from audio_to_text_mapping.csv.
Two key metrics are calculated:
Character Error Rate (CER): Measures the number of character-level errors.
Accuracy: Measures the percentage of correctly transcribed words.
Results Display:

The script prints CER and accuracy for each audio file.
