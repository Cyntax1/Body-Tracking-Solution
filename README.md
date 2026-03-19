# Body Tracking Solution

Real-time, multi-modal body tracking using Python and MediaPipe. Tracks **pose** (33 points), **hands** (42 points), and **face** (468 points) simultaneously with live analysis overlay and a digital human model view.

## Features

- **Pose Tracking** — Joint angle calculations for elbows, knees, hips
- **Hand Tracking** — Individual finger extension detection for both hands
- **Face Mesh** — 468-point face mesh with eye, lip, and contour highlighting
- **Digital Model** — Real-time wireframe reconstruction on a separate window
- **Live Analysis** — On-screen overlay showing all tracked metrics

## Demo

The program opens two windows:
1. **Comprehensive Analysis** — Camera feed with landmark overlay and metrics
2. **Digital Model** — Wireframe body reconstruction on a black background

## Requirements

```bash
pip install opencv-python mediapipe numpy
```

## Usage

```bash
python body_tracker.py
```

Press `q` or `ESC` to quit.

## How It Works

The system runs three MediaPipe models simultaneously:
- `mp.solutions.pose` — 33 skeletal landmarks
- `mp.solutions.hands` — 21 landmarks per hand (up to 2 hands)
- `mp.solutions.face_mesh` — 468 facial landmarks with refined eye/lip tracking

Joint angles are calculated using inverse trigonometry between landmark triplets. Finger extension is determined by comparing PIP-to-tip angles against threshold values.

## License

MIT
