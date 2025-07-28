# SSVEP and MI Tasks Based EEG Dataset for Artifact Removal

This dataset contains EEG recordings for Steady-State Visual Evoked Potential (SSVEP) and Motor Imagery (MI) tasks, including both clean and noisy conditions.

## Dataset Overview

- **Sampling Rate**: 1000 Hz
- **Data Types**:
  - SSVEP task data
  - MI task data (with various conditions)
  - Clean and noisy versions available

## SSVEP Task Data

### Experimental Setup
- **Display Configuration**:
  - Intro text centered at (display_width/2, 250)
  - Info text centered at (display_width/2, 100)
  
- **Timing Parameters**:
  - Hint display time: 0.5s
  - Inter-stimulus interval: 0.5s
  - Flash stimulation time: 5.0s
  - Rest time between trials: 0.5s
  - Inter-block interval: 10.0s
  - Data acquisition delay: 0.5s

- **Stimulus Configuration**:
  - Hint position: [740, 647]
  - Hint dimension: [125, 125] pixels
  - Line width: 8 pixels
  - Hint color: Red (255,0,0)

### Task Protocol
10 training rounds with the following instructions:
1. "请保持注视目标，避免运动" (4 trials)
2. "请摇摇头" (2 trials - head movement)
3. "请咬咬牙" (2 trials - teeth clenching)
4. "请眨眨眼" (2 trials - eye blinking)

## MI Task Data

### Experimental Setup
- **Recording Parameters**:
  - 32 channels
  - Sampling rate: 1000 Hz
  - Data saved in compressed format (ZipStorage)

### Task Groups and Conditions
The MI experiment includes the following task conditions with left/right variations:

1. **Basic Motor Imagery**:
   - 'miL' (left hand) × 5
   - 'miR' (right hand) × 5

2. **Artifact-Contaminated Conditions**:
   - Teeth clenching MI ('teethmiL'/'teethmiR') × 5 each
   - Eye blinking MI ('blinkmiL'/'blinkmiR') × 5 each
   - Head shaking MI ('shakemiL'/'shakemiR') × 5 each
   - Sweating condition MI ('sweatmiL'/'sweatmiR') × 5 each

3. **Control Conditions**:
   - Rest periods
   - Preparation phases (presweat, preshake)

### Experimental Protocol
The complete session consists of:
- 6 blocks alternating between MI and rest
- Teeth MI and rest
- Blink MI and preparation for shaking
- Shake MI blocks
- Preparation for sweating
- 2 Sweat MI blocks

Each block begins with an instructional prompt displayed for 5 seconds, followed by the task execution (6s per trial).

### Audio Cues
- Different sounds for left/right cues:
  - `voice_left.mp3` for left hand tasks
  - `voice_right.mp3` for right hand tasks

## File Organization
Data is organized with:
- Timestamp in filename
- Subject identifier
- Separate files for EEG data and event markers

## Data Format
- EEG data stored in compressed format
- Event markers saved in text files with columns:
  - Timestamp
  - Event type

## Usage Notes
1. For SSVEP data, focus on the 5s flash periods
2. For MI data, note the different artifact conditions
3. The first 5 seconds of each block contain baseline data
4. Randomization seed was fixed (seed=0) for reproducibility

## Quality Control
- Initial 5-second signal check performed
- Variance displayed for signal quality verification
