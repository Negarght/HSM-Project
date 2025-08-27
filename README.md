# High-Temperature Stage Microscopy (HSM) Software

---

This repository contains the custom-built **High-Temperature Stage Microscopy (HSM) software**, developed to automate the analysis of material behavior under controlled high-temperature conditions (up to 1400°C). The software leverages **computer vision** and **data analytics** to track critical thermal stages in real-time.

---

## Key Features

* Full automation of HSM tests, from capturing images to generating reports.
* Real-time tracking of **deformation, spherical, hemispherical, and flow stages**.
* Measurement of sample metrics: area, height, width, form factor, and more.
* PDF reports, Excel summaries, and captured images for detailed analysis.
* Supports multiple HSM sample types, with custom algorithms for different materials.
* Integration of temperature profiles and real-time visualization during testing.

---

## Folder Structure

```
HSM_Project/
│
├── main.py              # Main application logic
├── socket.py            # Communication with HSM hardware
├── camera.py            # Camera interface and image capture
├── pdf.py               # PDF report generation
├── get_spline.py        # Spline calculation for measurements
├── model.py             # Database models
├── xz_rc.py             # UI recognition and processing
├── ui/                  # QtDesigner UI files
└── HSM_Test_Example/    # Example test results
```

---

## HSM Test Example

This folder demonstrates automated results from a **recent HSM test** on **818 Mold Powder**. It showcases the software's capabilities for real-time monitoring and analysis.

**Included files:**

* `Test_Report.pdf`: Summary of test conditions, characteristic temperatures, and automated measurements (area, form factor, width, height, etc.).
* `Images/`: Captured images of the sample at different thermal states.
* `Graphs/`: Temperature profiles and statistical charts of the sample during testing.

**Stages Highlighted:**

1. **Initial Stage**: Binary image of the sample before any deformation. Baseline metrics are established.
2. **Deformation Stage** (e.g., 1115.8°C): Corners start rounding, and volume reduces. Real-time detection with OpenCV.
3. **Spherical Stage** (e.g., 1255.95°C, 1136.5°C): Width and height equalize or shape becomes a sphere. Detected using curvature and Hough Transform.
4. **Hemispherical Stage** (e.g., 1150°C): Sample forms a hemispherical shape. Height and area continuously monitored.
5. **Flow Stage** (e.g., 1157°C): Width becomes three times the height. Test is automatically stopped when flow condition is detected.

---

## Notes

* The software is highly dependent on HSM hardware for real-time data capture.
* All image processing modules rely on pre-configured camera APIs (`gxwrapper`, `dxwrapper`, `gxiapi`, `gxidef`) provided by the manufacturer.
* Full ownership of the project belongs to **Dama Pajouh Arvin Company**.

---



