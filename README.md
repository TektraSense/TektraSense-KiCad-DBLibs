![Status](https://img.shields.io/badge/status-active-brightgreen)

# TektraSense KiCad Database Libraries

This repository serves as the **centralized and version-controlled home for all KiCad database libraries** used in TektraSense hardware projects. It includes a comprehensive collection of symbols, footprints, and associated 3D models, all managed through a robust database-driven approach.

---

## 🌟 Purpose & Features

-   **Centralized Component Management:** Provides a single source of truth for all KiCad components, ensuring consistency across designs.
-   **Version Controlled:** All library updates are tracked, allowing for easy rollback and collaboration.
-   **Database-Driven:** Leverages KiCad's database library feature for efficient component management and part selection.
-   **Includes:**
    -   **Schematic Symbols:** Custom and adapted symbols.
    -   **Footprints:** PCB footprints for various component packages.
    -   **3D Models:** Corresponding 3D models for visualization and mechanical design.
-   **Integration Ready:** Designed for seamless integration with KiCad projects.

---

## 🚧 Development Status

This repository is **active and continually updated** as new components are designed or existing ones are revised. Components are added and maintained to support ongoing hardware development within TektraSense.

---

## 🛠️ Tech & Tools

-   **EDA Software:** KiCad 7.0+ (utilizing Database Libraries feature)
-   **Database Backend:** PostgreSQL (expected to be populated by the `kicad-component-pipeline` project)
-   **Library Format:** KiCad's native library formats (`.kicad_sym`, `.kicad_mod`), with references to a PostgreSQL database for component parameters.

---

## 🚀 Getting Started

### Prerequisites

-   **KiCad 7.0 or higher** installed on your system.
-   **Access to the TektraSense PostgreSQL database** (which stores the component parameters and is populated by the `kicad-component-pipeline`).

### Integration with KiCad

1.  **Clone this repository** to your local machine:
    ```bash
    git clone [https://github.com/TektraSense/TektraSense-KiCad-DBLibs.git](https://github.com/TektraSense/TektraSense-KiCad-DBLibs.git)
    ```
    (Replace `https://github.com/TektraSense/TektraSense-KiCad-DBLibs.git` with the actual URL of your repository.)

2.  **Open KiCad** and go to `Preferences` > `Configure Paths...`.
    -   Add a new environment variable, e.g., `TEKTRASENSE_KICAD_LIBS`, pointing to the cloned directory (`path/to/TektraSense-KiCad-DBLibs`).

3.  **Add the Database Library in KiCad:**
    -   Go to `Preferences` > `Manage Symbol Libraries...` (or `Manage Footprint Libraries...`).
    -   Click on the "Add existing library to table" icon.
    -   Select the `.kicad_dbl` file located in your cloned `TektraSense-KiCad-DBLibs` directory.
    -   Ensure the database connection details within the `.kicad_dbl` file are correctly configured to point to your PostgreSQL instance.

---

## 🤝 Contributing

Contributions are managed internally by the TektraSense hardware team. For external inquiries or contributions, please contact the repository maintainers.

---

Feel free to adjust any specific details or add more sections as needed! Do you want to refine any particular part of this `README.md`?
