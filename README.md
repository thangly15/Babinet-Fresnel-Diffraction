# Verification of Babinet’s Principle via Fresnel Diffraction

This project experimentally verifies Babinet's Principle by comparing the Fresnel diffraction patterns of a 0.4 mm single slit and a complementary opaque razor obstruction of equal width. 

## Hardware & Data Acquisition
Data was collected using a custom automated hardware pipeline:
*   **Optics:** He-Ne laser (632.8 nm), spatial filter, and a 25 µm photomultiplier tube (PMT) detector.
*   **Motion Control & Measurement:** A Newport MM3000 motorized translation stage and Keithley 6485 picoammeter.
*   **Automation:** Python `PyVISA` was used to establish serial communication, automate the spatial scanning, and stream live PMT current readings directly into a Jupyter Notebook environment.

## Theoretical Modeling
The experimental intensity distributions were fitted to a scalar diffraction model using `SciPy` Fresnel integrals. To account for the finite spatial resolution of the PMT slit (25 µm), the theoretical model was convolved with a detector response function (Tukey window) using `scipy.signal.convolve`.

## Results
The fitted results for both the slit and razor configurations showed strong agreement with theory, confirming that diffraction depends on the geometry of the obstruction rather than whether light is transmitted or blocked.

### Single Slit Diffraction (Convolved)
![Single Slit Convolved](IntensityProfSlitConv (1).png)

### Razor Obstruction Diffraction (Convolved)
![Single Strip Convolved](IntensityProfStripConv (1).png)

For the complete methodology and mathematical breakdown, please see the [Final Project Report](Verification_of_Babinet_s_Principle_via_Fresnel_Diffraction_of_a_Single_Slit-compressed.pdf).
