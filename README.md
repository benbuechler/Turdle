# Turdle — Autonomous Pet Waste Collector

A small outdoor mobile robot that patrols lawns, detects pet waste, and safely collects it into a sealed container. Think "Roomba for yards," tuned for detection, bio‑safety, and lawn‑friendly navigation.

![Hero Image](docs/hero.png)

\## ✨ Project goals

\- **Detect**: Robust visual detection of pet waste on grass (sun, shade, dew, snow remnants).

\- **Navigate**: Lawn‑safe path planning; avoid flowerbeds, pets, and obstacles.

\- **Collect**: Mechanical pickup that minimizes smear/spread and auto‑bags waste.

\- **Safety**: Biohazard handling, child/pet interaction safeguards, privacy by design.

\- **Open Collaboration**: Modular hardware + software so teams can swap components.

\## 📦 Tech stack (proposed)

\- **Compute**: Jetson Nano/Orin Nano or Raspberry Pi 5 + Coral TPU

\- **Robot Middleware**: ROS 2 (Humble/Iron) or micro‑ROS for MCU coordination

\- **Perception**: YOLOv8/Detectron2; on‑device inference

\- **Navigation**: SLAM (RTAB‑Map/Cartographer), depth camera + wheel encoders, optional RTK GNSS

\- **Firmware**: ESP32/STM32 for motor drivers, sensors, interlocks

\- **Simulation**: Gazebo (Fortress) with lawn terrains & lighting variants

\## 📸 Datasets

We host **small samples** in `datasets/samples/` and link full datasets via Releases or an external bucket. See `datasets/annotation_guidelines.md`.

\## 🧰 Getting started

\```bash

\# 1) Clone

git clone https://github.com/YOUR_ORG/poopbot.git && cd poopbot

\# 2) Dev setup (example: ROS 2 + Python)

./scripts/bootstrap.sh # installs deps, precommit, sets up venv

pre-commit install

\# 3) Build & run sim (example)

colcon build --symlink-install

source install/setup.bash

ros2 launch simulation gazebo_lawn.launch.py

\# 4) Run vision demo (CPU)

python software/edge/vision/demo_detect.py --images datasets/samples
