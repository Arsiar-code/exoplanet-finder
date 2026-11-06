# Exoplanet Finder

A hands-on learning project: automating a reproducible Linux setup with **Ansible** and using it to explore real NASA light-curve data with **Python** and **Jupyter**.

## Goal

Exoplanets can be detected with the *transit method*: when a planet passes in front of its star, the star's brightness drops slightly and regularly. This project builds the whole analysis environment automatically and then looks for those dips in public Kepler/TESS data.

## Tech stack

- Ubuntu on WSL2 (Windows Subsystem for Linux)
- Ansible (inventory + playbooks, run against localhost)
- Python 3 with a virtual environment (venv)
- JupyterLab, NumPy, pandas, Matplotlib, [lightkurve](https://github.com/lightkurve/lightkurve)
- Git & GitHub (SSH key authentication)
- Ansible Vault (experimented with encrypted secrets) (soon to be added)

## Project structure

```
exoplanet-finder/
├── ansible/
│   ├── hosts.ini             # inventory: where Ansible runs (localhost)
│   ├── python-packages.yml   # playbook: installs Python, venv and pip
│   └── virtualenv.yml        # playbook: builds the venv with Jupyter and libraries
├── notebooks/
│   └── first-lightcurve.ipynb  # first analysis: Kepler-10 light curve
├── README.md
├── LICENSE
└── .gitignore                # venv/ and secrets are not committed
```

## Getting started

```bash
git clone git@github.com:Arsiar-code/exoplanet-finder.git
cd exoplanet-finder

# 1. System packages (Python, venv, pip)
ansible-playbook -i ansible/hosts.ini ansible/python-packages.yml

# 2. Virtual environment with JupyterLab and analysis libraries
ansible-playbook -i ansible/hosts.ini ansible/virtualenv.yml
```

Afterwards, open the notebook in VS Code (or JupyterLab) and select the Python interpreter from `venv/`.

## Results so far

The first notebook searches the NASA archive via lightkurve, downloads Kepler observations of **Kepler-10** (a star with confirmed planets) and plots its normalized light curve.

<img width="899" height="484" alt="Screenshot 2026-11-05 182756" src="https://github.com/user-attachments/assets/b8feff0d-1271-4486-ab5d-64c177c80fcb" />

## Why this project

I built this to learn Linux automation by doing, combining my interest in Linux with my curiosity about space.
