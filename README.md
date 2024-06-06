# Speaker-Diarization using PyAnnote and Whisper
##Library Installation:

Installing the latest development version of SpeechBrain ensures you have the newest features and bug fixes.
Installing a specific stable version of SpeechBrain ensures compatibility if the development version has issues.
pydub and ffmpeg are installed to handle audio manipulation and conversion.
##File Upload:

The google.colab.files module is used to upload audio files from the local machine to Google Colab.
The uploaded dictionary stores the uploaded files, and path extracts the file path of the first uploaded file.
##Audio Deserialization:

AudioSegment.from_file loads the audio file into an AudioSegment object for manipulation.
The function deserialize_audio prints the audio properties (channels, frame rate, sample width, duration) for verification.
##Volume Adjustment:

The volume of the audio is increased by 10dB using the + operator on the AudioSegment object.
The manipulated audio is saved to a new file.
##Speaker Recognition:

The speechbrain library is used to load a pretrained speaker recognition model (spkrec-ecapa-voxceleb).
The audio signal is loaded using torchaudio.load, and embeddings are obtained using the encode_batch method.
##Device Setup:

Checks if a GPU is available and sets the device for PyTorch accordingly, enabling GPU acceleration if available.
##Speaker Diarization:

The pyannote.audio library is used to initialize the speaker diarization pipeline with GPU support.
The diarization process is performed on the audio file, and the time taken is measured.
##Transcription:

The Whisper model (large-v3) is loaded with GPU support for transcription.
Transcription is performed on the audio file, and the time taken is measured.
Transcription segments are extracted from the result.
##Mapping Transcriptions to Speakers:

A set processed_segments is initialized to keep track of processed transcription segments to avoid duplication.
Iterates through diarization results and maps each transcription segment to the corresponding speaker based on time overlap.
Transcription texts are joined together for each speaker and printed.
