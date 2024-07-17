⚠️ *Warning: This website may not function properly on Safari. For the best experience, please use Google Chrome.*

[`arXiv`](https://arxiv.org/pdf/2404.10301): Stable Audio Open paper

[`HuggingFace`](https://huggingface.co/stabilityai/stable-audio-open-1.0): model weights

[`stable-audio-tools`](https://github.com/Stability-AI/stable-audio-tools): code to reproduce Stable Audio

[`stable-audio-metrics`](https://github.com/Stability-AI/stable-audio-metrics): code to evaluate Stable Audio

Stable Audio Open generates variable-length (up to 47s) stereo audio at 44.1kHz from text prompts. It comprises three components: an autoencoder that compresses waveforms into a manageable sequence length, a T5-based text embedding for text conditioning, and a transformer-based diffusion (DiT) model that operates in the latent space of the autoencoder.

## Generations by the Stable Audio Open community

asdf

## Generations from AudioCaps prompts

**Prompt**: Calming instrumental music primarily on piano can be used for relaxing.

| Our Model | MusicGen-large-stereo | Ground-truth | 
| --------- | -------------- | --------------- | 
| <audio controls preload=False><source src="audio/1091_sa2.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/1091_musicgen.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/1091.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> |


## Generations from Song Describer Dataset prompts

**Prompt**: An uplifting jazz song that makes your head shake. 

| Our Model (stereo, 44.1kHz) | MusicGen-large-stereo (stereo, 32kHz) | 
| --------- | ---------------------- | 
| <audio controls preload=False><source src="audio/1001_sa2.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/1001_musicgen.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> |

**Prompt**: One cannot avoid moving the feet and neck listening to this fast and loopy brazilian tune.

| Our Model | MusicGen-large-stereo  | 
| --------- | ---------------------- | 
| <audio controls preload=False><source src="audio/94_sa2.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/94_musicgen.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> |

**Prompt**: Ambiental song that evokes calm with a progression of stereo electronic elements.

| Our Model | MusicGen-large-stereo  | 
| --------- | ---------------------- | 
| <audio controls preload=False><source src="audio/906_sa2.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/906_musicgen.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> |

**Prompt**: This song starts with a ukulele and builds up with percussion using claps and an acoustic guitar that plays the same rhythm as the ukulele with melody played on a xylophone and has a very upbeat feel to it.

| Our Model (stereo, 44.1kHz) | MusicGen-large-stereo (stereo, 32kHz) | Ground-truth (stereo, 44.1kHz) | 
| --------- | -------------- | --------------- | 
| <audio controls preload=False><source src="audio/1069_sa2.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/1969_musicgen.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/1069.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> |

**Prompt**: Calming instrumental music primarily on piano can be used for relaxing.

| Our Model | MusicGen-large-stereo | Ground-truth | 
| --------- | -------------- | --------------- | 
| <audio controls preload=False><source src="audio/1091_sa2.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/1091_musicgen.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/1091.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> |

**Prompt**: A dance music club banger, with a heavy kick, subtle supporting percussion like tabla and bongos, prominent pop synth lines, and a repetitive hook.

| Our Model | MusicGen-large-stereo | Ground-truth | 
| --------- | -------------- | --------------- | 
| <audio controls preload=False><source src="audio/3_sa2.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/3_musicgen.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/3.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> |

These prompts/audios were used for the qualitative study we report in our paper.

## Memorization analysis

Recent works examined the potential of generative models to memorize training data, especially for repeated elements in the training set. Adhering to principles of responsible model development, we also run a comprehensive study on memorization. 

In light of the possible risk of memorizing repeated audio within the training set, we start by studying if our dataset contains repeated data. We embed all our training data using the LAION-CLAP audio encoder to select audios that are close in this space based on a manually set threshold. The threshold is set such that the selected audio correspond to exact replicas. With this process, we identify 3,693 Freesound and 856 FMA repeated audios.

Our methodology is based on comparing our model's generations against the training set in LAION-CLAP space. We then select the top-50 generations that are closest to the training data (the memorization candidates) and listen.  We listened to memorization candidates generated with prompts from the identified repeated data in our training set, and did not find memorization. We also listened to memorization candidates from 11,000 random prompts from the training set, and did not find memorization. We even listened to memorization candidates from outstanding generations, and did not find memorization. 
The most interesting memorization candidates, together with their closest training data, are listed here. We extensively listened to potential memorization candidates, and **could not find memorization**. Those are the most interesting candidates from training data prompts:


| Generation by our model | Closest training data  | Prompt |
| ----------------------- | ----------- | ------ |
| <audio controls preload=False><source src="audio/clarinet.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <a href="https://freesound.org/people/MTG/sounds/357181/">link</a>| Scale, clarinet, Asharpmajor, neumann-U87, good-sounds.  |
| <audio controls preload=False><source src="audio/noise.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <a href="https://freesound.org/people/OldSlowVideogamer/sounds/366116/">link</a>| Disturb, no-signal, tv, noise, radio, high-disturbance, frequency-jam, white-noise. |
| <audio controls preload=False><source src="audio/drumloop2.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <a href="https://freesound.org/people/bcnlab/sounds/270756/">link</a>| 120, bpm, beat, Drums, blues, loop. |
| <audio controls preload=False><source src="audio/rain.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <a href="https://freesound.org/people/ionisaattor/sounds/256173/">link</a>|  Thunder, storm, field-recording, rain. |
| <audio controls preload=False><source src="audio/violin.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <a href="https://freemusicarchive.org/music/Kosta_T/__________________/Kosta_T_-__-_03____-/">link</a>|   Avant-garde, improv, contemporary classical, instrumental. |
| <audio controls preload=False><source src="audio/piano.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <a href="https://freemusicarchive.org/music/Unheard_Music_Concepts/Industry/10_The_Trail/">link</a>|  Piano, modern jazz, minimalism, instrumental. |
| <audio controls preload=False><source src="audio/drumloop.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <a href="https://freesound.org/people/stoltingmediagroup/sounds/596826/">link</a>|  160-BPM, kick-hat-snare, drumloop. |
| <audio controls preload=False><source src="audio/1k.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <a href="https://freesound.org/people/Sean_hay_ca/sounds/174551/">link</a>|  1000Hz 48k sample rate MP3. |


## Autoencoder: reconstructions

This comparison is useful to evaluate the audio fidelity capabilities of the autoencoder. On the left, we have the ground truth recording. On the right, we take the ground truth recording and end pass it through the autoencoder. Note that the autoencoder reconstruction is fairly transparent, very close to the ground truth.

| Ground truth | Autoencoder reconstruction |
| ------------ | -------------------------- |
|<audio controls preload=False><source src="audio/226.mp3" type="audio/mpeg">Audio not supported by your browser.</audio><br>|<audio controls preload=False><source src="audio/226.wav" type="audio/mpeg">Audio not supported by your browser.</audio><br>|
|<audio controls preload=False><source src="audio/3112.mp3" type="audio/mpeg">Audio not supported by your browser.</audio><br>|<audio controls preload=False><source src="audio/3112.wav" type="audio/mpeg">Audio not supported by your browser.</audio><br>|
|<audio controls preload=False><source src="audio/3453.mp3" type="audio/mpeg">Audio not supported by your browser.</audio><br>|<audio controls preload=False><source src="audio/3453.wav" type="audio/mpeg">Audio not supported by your browser.</audio><br>|
|<audio controls preload=False><source src="audio/4880.mp3" type="audio/mpeg">Audio not supported by your browser.</audio><br>|<audio controls preload=False><source src="audio/4880.wav" type="audio/mpeg">Audio not supported by your browser.</audio><br>|
|<audio controls preload=False><source src="audio/4883.mp3" type="audio/mpeg">Audio not supported by your browser.</audio><br>|<audio controls preload=False><source src="audio/4883.wav" type="audio/mpeg">Audio not supported by your browser.</audio><br>|
|<audio controls preload=False><source src="audio/5084.mp3" type="audio/mpeg">Audio not supported by your browser.</audio><br>|<audio controls preload=False><source src="audio/5084.wav" type="audio/mpeg">Audio not supported by your browser.</audio><br>|
|<audio controls preload=False><source src="audio/5089.mp3" type="audio/mpeg">Audio not supported by your browser.</audio><br>|<audio controls preload=False><source src="audio/5089.wav" type="audio/mpeg">Audio not supported by your browser.</audio><br>|
|<audio controls preload=False><source src="audio/5339.mp3" type="audio/mpeg">Audio not supported by your browser.</audio><br>|<audio controls preload=False><source src="audio/5339.wav" type="audio/mpeg">Audio not supported by your browser.</audio><br>|
|<audio controls preload=False><source src="audio/5340.mp3" type="audio/mpeg">Audio not supported by your browser.</audio><br>|<audio controls preload=False><source src="audio/5340.wav" type="audio/mpeg">Audio not supported by your browser.</audio><br>|
|<audio controls preload=False><source src="audio/5341.mp3" type="audio/mpeg">Audio not supported by your browser.</audio><br>|<audio controls preload=False><source src="audio/5341.wav" type="audio/mpeg">Audio not supported by your browser.</audio><br>|
|<audio controls preload=False><source src="audio/5343.mp3" type="audio/mpeg">Audio not supported by your browser.</audio><br>|<audio controls preload=False><source src="audio/5343.wav" type="audio/mpeg">Audio not supported by your browser.</audio><br>|


