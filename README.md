## Supernova Neutrino Event Analysis

A comprehensive machine learning framework for analyzing supernova neutrino events detected in Liquid-Argon Time-Projection Chambers (LArTPCs). This project implements deep learning methods to classify neutrino events, predict energies, and simulate realistic detector conditions for the Supernova Early Warning System (SNEWS).

---

### Motivations

Supernova neutrinos are important. They arrive ~3 hours before visible light does from supernovae, and thus provide us with an early warning for supernova events. As supernova are rare and provide insightful spectroscopy data on high-pressure, high-energy Physics, it is ideal that we can observe as many events as possible. 

The issue stands that neutrinos, with their low mass and lack of electric charge, are extremely difficult to detect, requiring large, expensive and highly sensitive measurement systems such as Fermilab's MicroBooNE Liquid Argon Time Projection Chamber (LArTPC). These chambers utilise ionization tracks in liquid argon to produce high-resolution 3D images of particle interactions. Due to the LArTPC's high sensitivity, it is susceptible to noise in its images in the form of electronic (sensors) and radiation (Argon and Radon from detector materials). 

This project's aim is to apply Convolutional Neural Networks to successfully identify supernova neutrino occurrences in the presence of electronic and radiological noise from simulated LArTPC data, as well as extract important information including neutrino energy and particle interaction count.

---

### Datasets

The data for this mini-project comes in the form of the following files:

| File | Description |
| ----------- | ----------- |
| larImages.npy | A numpy array of 10,000 100x100 pixel images |
| meta.npy | The meta information about the particles in the image |

The images show the energy deposited in the liquid argon detector in a small slice of space and time. The meta information contains the following 64 numbers for each image. The [PDG code](https://pdg.lbl.gov/2019/reviews/rpp2019-rev-monte-carlo-numbering.pdf) uses a Monte-Carlo numbering scheme to identify the particle type (e.g electron=11, electron-neutrino=12, etc.)

| Column | Description |
| ----------- | ----------- |
| 0 | Row number |
| 1 | Neutrino Energy (MeV) |
| 2 | Initial state particles (always 2) |
| 3 | Final state particles (varies) |
| 4-8 | Initial Particle 1: PDG code, Total Energy (MeV), $p_x$, $p_y$, $p_z$ | 
| 9-13 | Initial Particle 2: PDG code, Total Energy (MeV), $p_x$, $p_y$, $p_z$ |
| 14-18 | Final Particle 1: PDG code, Total Energy (MeV), $p_x$, $p_y$, $p_z$ | 
| 19-23 | Final Particle 2: PDG code, Total Energy (MeV), $p_x$, $p_y$, $p_z$ |
| $\vdots$ | Final Particle N: PDG code, Total Energy (MeV), $p_x$, $p_y$, $p_z$ |
| 59-63 | Final Particle 10: PDG code, Total Energy (MeV), $p_x$, $p_y$, $p_z$ |
