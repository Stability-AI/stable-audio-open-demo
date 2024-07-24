⚠️ *Warning: This website may not function properly on Safari. For the best experience, please use Google Chrome.*

[`arXiv`](https://arxiv.org/abs/2407.14358): Stable Audio Open paper

[`HuggingFace`](https://huggingface.co/stabilityai/stable-audio-open-1.0): model weights

[`stable-audio-tools`](https://github.com/Stability-AI/stable-audio-tools): code to reproduce Stable Audio

[`stable-audio-metrics`](https://github.com/Stability-AI/stable-audio-metrics): code to evaluate Stable Audio

Stable Audio Open generates variable-length (up to 47s) stereo audio at 44.1kHz from text prompts. It comprises three components: an autoencoder that compresses waveforms into a manageable sequence length, a T5-based text embedding for text conditioning, and a transformer-based diffusion (DiT) model that operates in the latent space of the autoencoder.

## Generations by the community

**Prompt**: Pinball bumper.

<audio controls preload=False><source src="audio/paintball.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> 

**Prompt**: 80s drum beat.

<audio controls preload=False><source src="audio/drums80s.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> 

**Prompt**: 80s bass guitar.

<audio controls preload=False><source src="audio/bass80s.mp3" type="audio/mpeg">Audio not supported by your browser.</audio>

**Prompt**: Slap mandolin.

<audio controls preload=False><source src="audio/slap.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> 


## Generations from AudioCaps prompts

**Prompt**: Rain is falling and hitting surfaces and then splashing into puddles.

| Stable Audio Open | Stable Audio 2.0 | AudioLDM2-48kHz | 
| --------- | -------------- | --------------- | 
| <audio controls preload=False><source src="audio/103058_sao.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/103058_sa2.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/103058_aldm248.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> |

**Prompt**: A train horn goes off loudly.

| Stable Audio Open | Stable Audio 2.0 | AudioLDM2-48kHz | 
| --------- | -------------- | --------------- | 
| <audio controls preload=False><source src="audio/11080_sao.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/11080_sa2.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/11080_aldm248.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> |

**Prompt**: Gurgling and splashing water.

| Stable Audio Open | Stable Audio 2.0 | AudioLDM2-48kHz | 
| --------- | -------------- | --------------- | 
| <audio controls preload=False><source src="audio/103075_sao.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/103075_sa2.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/103075_aldm248.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> |

**Prompt**: An engine throttles and clanks and then suddenly accelerates off into the distance.

| Stable Audio Open | Stable Audio 2.0 | AudioLDM2-48kHz | 
| --------- | -------------- | --------------- | 
| <audio controls preload=False><source src="audio/103043_sao.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/103043_sa2.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/103043_aldm248.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> |


## Generations from Song Describer Dataset prompts

**Prompt**: A dance music club banger, with a heavy kick, subtle supporting percussion like tabla and bongos, prominent pop synth lines, and a repetitive hook.

| Stable Audio Open | Stable Audio 2.0 | MusicGen-large-stereo | 
| --------- | -------------- | --------------- | 
| <audio controls preload=False><source src="audio/3_sao.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/3_sa2.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/3_musicgen.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> |

**Prompt**: A danceable electronic track in the genre of dance

| Stable Audio Open | Stable Audio 2.0 | MusicGen-large-stereo | 
| --------- | -------------- | --------------- | 
| <audio controls preload=False><source src="audio/24_sao.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/24_sa2.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/24_musicgen.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> |

**Prompt**: Fast beat, hip hop, upbeat that has a positive vibe.

| Stable Audio Open | Stable Audio 2.0 | MusicGen-large-stereo | 
| --------- | -------------- | --------------- | 
| <audio controls preload=False><source src="audio/28_sao.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/28_sa2.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/28_musicgen.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> |

**Prompt**: An instrumental song which employs a worldbeat element through its eerie percussion

| Stable Audio Open | Stable Audio 2.0 | MusicGen-large-stereo | 
| --------- | -------------- | --------------- | 
| <audio controls preload=False><source src="audio/38_sao.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/38_sa2.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/38_musicgen.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> |

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

## Autoencoder reconstructions

This comparison is useful to evaluate the audio fidelity capabilities of the autoencoder. On the left, we have the ground truth recording. On the right, we take the ground truth recording and end pass it through the any of those autoencoders or neural audio codecs. 

| Ground truth | Stable Audio Open | Stable Audio 2.0 | DAC | 
| ------------ | ----------------- | ---------------- | --- |
| <audio controls preload=False><source src="audio/3112.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/3112_sdd_sao.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/3112_sdd_sa2.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/3112_sdd_dac.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> |
| <audio controls preload=False><source src="audio/4883.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/4883_sdd_sao.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/4883_sdd_sa2.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/4883_sdd_dac.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> |
| <audio controls preload=False><source src="audio/5084.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/5084_sdd_sao.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/5084_sdd_sa2.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/5084_sdd_dac.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> |
| <audio controls preload=False><source src="audio/226.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/226_sdd_sao.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/226_sdd_sa2.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/226_sdd_dac.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> |
| <audio controls preload=False><source src="audio/C2HinL8VlM.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/C2HinL8VlM_audiocaps_sao.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/C2HinL8VlM_audiocaps_sa2.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/C2HinL8VlM_audiocaps_dac.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> |
| <audio controls preload=False><source src="audio/9mgOkzm-xg.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/9mgOkzm-xg_audiocaps_sao.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/9mgOkzm-xg_audiocaps_sa2.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/9mgOkzm-xg_audiocaps_dac.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> |
| <audio controls preload=False><source src="audio/BSmz3SEW1w.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/BSmz3SEW1w_audiocaps_sao.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/BSmz3SEW1w_audiocaps_sa2.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> | <audio controls preload=False><source src="audio/BSmz3SEW1w_audiocaps_dac.mp3" type="audio/mpeg">Audio not supported by your browser.</audio> |
