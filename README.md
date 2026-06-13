# AIoT Surveillance Task Offloading Simulation

This repository contains the complete simulation code for the thesis:

"Reliable Offloading for AIoT based Surveillance Video Analytics: Design and Performance Analysis"
University of Electronic Science and Technology of China (UESTC)

## Features

- M/M/1 queue (exponential processing and inter-arrival times)
- Markov model for temporally correlated network quality
- Jitter in travel times (cloud: normal distribution mean 100 ms, std 10 ms; edge: normal distribution mean 2 ms, std 0.5 ms)
- Packet loss with retransmission (cloud 1%, edge 0.1%)
- Variable task size (log-normal distribution)
- Corrected energy rule: low battery -> MEC (0.5 J per task) instead of cloud (2.0 J per task)
- Six offloading strategies: CloudOnly, AlwaysMEC, Random, ContextAware, StaticThreshold, LocalOnly
- Statistical validation: 30 to 100 independent runs, 95% confidence intervals, t-tests, Cohen's d

## How to Run

1. Clone the repository:
   git clone https://github.com/AyeshaRasool606/aiot-surveillance-offloading.git
   cd aiot-surveillance-offloading

2. Install dependencies:
   pip install -r requirements.txt

3. Run the main simulation:
   python simulation.py

The script will run 30 independent runs x 200 jobs for all strategies and print a comparison table with mean latency, 95% confidence intervals, MEC usage, and energy per task.

## Dependencies

- simpy
- numpy
- scipy
- stable-baselines3 (optional, for DQN comparison)
- gymnasium (optional, for DQN training)

## Repository Structure

aiot-surveillance-offloading/
├── simulation.py          # Main simulation code (all strategies)
├── requirements.txt       # Python dependencies
├── LICENSE                # MIT License
└── README.md              # This file

## Citation

If you use this code in your research, please cite:

@mastersthesis{Rasool2026,
  author = {Ayesha Rasool},
  title = {Reliable Offloading for AIoT based Surveillance Video Analytics: Design and Performance Analysis},
  school = {University of Electronic Science and Technology of China},
  year = {2026},
  doi = {10.5281/zenodo.20681906}
}

## License

MIT License – free for academic and commercial use with attribution.
