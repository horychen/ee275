# EE275 - Motor Control Simulation Tutorials

Course materials for EE275.

## Prerequisites

- [Anaconda](https://www.anaconda.com/download) or [Miniconda](https://docs.conda.io/en/latest/miniconda.html) installed

## Setup

### Option A: Using environment.yml (recommended)

```bash
conda env create -f environment.yml
conda activate ee275
```

### Option B: Manual setup with requirements.txt

```bash
conda create -n ee275 python=3.10
conda activate ee275
pip install -r requirements.txt
```

## Running the Simulation

```bash
conda activate ee275
python tutorials_ep6_svpwm.py
```

The first run will be slow due to Numba JIT compilation. Subsequent runs are faster.

## Files

- `tutorials_ep6_svpwm.py` — Main simulation script (FOC + optional SVPWM inverter model)
- `tuner.py` — Auto-tuning module for PI controller gains
- `python_tutorial_cjh.ipynb` — Python tutorial notebook
- `sympy_tutorial_cjh.ipynb` — SymPy tutorial notebook

## SVPWM Toggle

SVPWM inverter simulation is controlled by `MACHINE_SIMULATIONs_PER_SAMPLING_PERIOD` in the user config dict inside `tutorials_ep6_svpwm.py`:

- **`1`** (default) — SVPWM is **OFF**, uses ideal voltage source. Fast simulation, good for beginners.
- **`>= 20`** (e.g., `500`) — SVPWM is **ON**, simulates carrier-based PWM with dead time. Slower but more realistic.
