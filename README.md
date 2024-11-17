# "Real-Time MRI Synthesis from Text Using a Two-Stage Pipeline for Pronunciation Training." 

## Dataset
### Data Preparation for TTS
For training the Tortoise-TTS model, text data is cleaned and normalized to remove inconsistencies, while paired audio recordings are segmented and normalized for volume and quality. Speaker embeddings are extracted from reference audios to capture vocal traits, enabling the TTS model to mimic the speaker's characteristics. Additionally, Mel spectrograms are generated as input representations, ensuring the audio-text alignment is precise and effective for training.

### Data Preparation for MRI Video Synthesis
The paired audio and MRI video datasets are preprocessed to maintain synchronization. Audio features MFCC are extracted. MRI videos are converted into individual frames, resized, and normalized for uniformity. Data augmentation enhances variability, and the dataset is split into training, validation, and testing subsets, ensuring comprehensive coverage of different speech patterns.


## Pipeline Model
The pipeline model consists of two stages: Text-to-Speech (TTS) and Speech-to-MRI video synthesis. In the first stage, Tortoise-TTS generates speech from text, incorporating speaker embeddings to replicate vocal traits. In the second stage, the synthesized audio is processed to extract Mel-Frequency Cepstral Coefficients (MFCCs), which are then mapped to MRI video frames using a Bidirectional LSTM network. This streamlined approach ensures synchronized and realistic audio-MRI video outputs, capturing natural articulatory movements.

   
### 1. Tortoise TTS
-> Give text and audio's folder path as input

-> Run the tortise_tts.py

-> Store results and use them in the second part

### 2. Mri Video Generation

-> Training: run the mri_train.py

-> Generation: run the generate_mri.py
