# Cognitive Modeling and Music Generation
**MUSI6001 Music Perception & Cognition | Spring 2023**

## Requirements

Additionally to the built-in colab packages
```
sudo apt install -y fluidsynth

pip install --upgrade pyfluidsynth
pip install pretty_midi
pip install librosa
pip install mingus
```

## Reproducing the Generation

Either use `music_generation.ipynb` in the repo or https://colab.research.google.com/drive/1JJ9FUqcM1tG73-OADmh0LpLYNnU9Z8ik?usp=sharing

## System Specification

The main system is a probabilistic system whose note probabilities are largely determined by the MUSACT model with some modifications. The major addition to the system are the inclusion of the diatonic seventh chords and proximity conditioning so that the distances between two adjacent notes are not too large. The underlying rhythm is partly rule-based and partly probabilistic where the probability of the length of a note depends on the current starting position of the note. I additionally have a clause to end the generation if the chord activation gives a perfect cadence. The rhythm of the last few notes are also fixed to give a more "normal" ending.

The output of the system is weirdly and surprisingly "normal" despite how simple the system is. The system sometimes end up with two keys a fifth apart that are almost equally activated causing the melody to be constantly modulating between the two. Very unscientifically speaking, the system sounds a little bit like a nervous jazz student improvising for the first time.

## Sample Audio

MIDI: `musgen-midi.zip` (50 files)

Wav: `musgen-wav/*.wav` (5 files)
