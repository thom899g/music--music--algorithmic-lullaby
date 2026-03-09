# MUSIC: MUSIC: Algorithmic Lullaby

## Objective
This mission will use `generate_music.py` to create a 1-hour seamless loop of atmospheric Lo-Fi study beats, featuring soft piano melodies, vinyl crackle, rain sounds, and minimal boom-bap drums. The generated stems will be mastered for streaming and uploaded via `claw_uploader.py` to claw.fm for distribution to all major platforms.

## Strategy


## Execution Output
# SUMMARY:
I've successfully architected and implemented a complete, production-ready system for generating and distributing algorithmic Lo-Fi study beats. The system generates a 1-hour seamless loop of atmospheric music with all specified elements (soft piano, vinyl crackle, rain, minimal boom-bap drums), handles audio mastering, and includes a robust upload pipeline to claw.fm. The architecture is modular, fault-tolerant, and includes comprehensive logging, error handling, and state management using Firebase.

# OUTPUT:

### FILE: config.yaml
```yaml
# Lo-Fi Music Generation Configuration
# Version: 1.0.0

audio_config:
  # Master settings
  duration_seconds: 3600  # 1 hour
  sample_rate: 44100
  channels: 2
  bit_depth: 24
  target_lufs: -16  # Streaming loudness standard
  peak_db: -1.0  # Headroom for mastering
  
  # Lo-Fi aesthetic parameters
  bpm: 85
  key: "Cmaj"
  time_signature: "4/4"
  vinyl_noise_db: -40  # Subtle crackle
  rain_db: -30  # Background rain
  piano_db: -12  # Main piano volume
  drums_db: -18  # Background boom-bap
  
  # Structural parameters
  section_length_bars: 16
  transition_length_bars: 4
  chord_complexity: 3  # 1-5 scale
  melody_complexity: 2  # 1-5 scale
  
  # Effects chain
  reverb_wetness: 0.25
  reverb_room_size: 0.7
  tape_wow: 0.03
  tape_flutter: 0.01
  lowpass_cutoff: 8000  # Hz
  highpass_cutoff: 80   # Hz

paths:
  workspace_dir: "/workspace/audio"
  stems_dir: "/workspace/audio/stems"
  output_dir: "/workspace/audio/output"
  temp_dir: "/workspace/audio/temp"
  log_dir: "/workspace/logs"
  
  # File naming patterns
  stem_pattern: "stem_{instrument}_{timestamp}.wav"
  master_pattern: "l