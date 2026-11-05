# Exoplanet Finder

A hands-on learning project: automating a reproducible Linux setup with **Ansible** and using it to search for exoplanets in real NASA light-curve data with **Python** and **Jupyter**.

## Goal

Exoplanets are detected via the *transit method*: when a planet passes in front of its star, the star's brightness drops slightly and regularly. This project sets up the whole analysis environment automatically and then looks for those dips in public Kepler/TESS data.

## Tech stack

- Ubuntu on WSL2 (Windows Subsystem for Linux)
- Ansible (inventory + playbook, run against localhost)
- Python 3, venv, pip
- Jupyter / lightkurve (planned)
- Git & GitHub (SSH key authentication)

## Project structure
