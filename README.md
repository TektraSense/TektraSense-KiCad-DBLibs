![Status](https://img.shields.io/badge/status-in_progress-yellow)

# TektraSense KiLibs

This repository serves as the **centralized and version-controlled home for all KiCad library assets** used in TektraSense hardware projects. It includes a comprehensive collection of symbols, footprints, and associated 3D models, all designed to be used with a database-driven workflow.

---

## 🌟 Purpose & Features

-   **Centralized Component Assets:** Provides a single source of truth for all KiCad library files, ensuring consistency across designs.
-   **Version Controlled:** All library updates are tracked via Git, allowing for easy rollback and team collaboration.
-   **Database-Driven:** Intended to be used with KiCad's database library feature, where component parameters are stored externally in a PostgreSQL database populated by the [kicad-component-pipeline](https://github.com/TektraSense/kicad-component-pipeline) project.
-   **Includes:**
    -   **Schematic Symbols (`.kicad_sym`):** Custom-made and adapted symbols organized into libraries.
    -   **Footprints (`.kicad_mod`):** PCB footprints for various component packages.
    -   **3D Models (`.step`, `.wrl`):** Corresponding 3D models for visualization and mechanical design.

---

## 🚧 Development Status

This repository is **active and continually updated** as new components are added to the library or existing ones are revised. All assets are maintained to support ongoing hardware development at TektraSense.

---

## 🛠️ Tech & Tools

-   **EDA Software:** KiCad 7.0+
-   **Database Backend:** This repository provides the library files (`.kicad_sym`, `.kicad_mod`) that are referenced by an external PostgreSQL database.
-   **Configuration:** A `.kicad_dbl` file is included to configure the connection between KiCad and the database.

---

## 🚀 Getting Started

### Prerequisites

-   **KiCad 7.0 or higher** installed on your system.
-   **Access to the TektraSense PostgreSQL database** (which is populated by the `kicad-component-pipeline`).
-   **PostgreSQL ODBC Driver** installed on your system.

### Installing the PostgreSQL ODBC Driver

KiCad requires an ODBC driver to communicate with a PostgreSQL database. You must install the appropriate driver for your operating system.

---
#### **macOS**
The recommended method for macOS is to use [Homebrew](https://brew.sh/).

1.  Open the **Terminal** application.
2.  Run the following command to install the driver:
    ```bash
    brew install psqlodbc
    ```
3.  Restart KiCad after the installation is complete.

---
#### **Windows**
For Windows, the best method is to use the official MSI installer.

1.  Go to the official PostgreSQL ODBC download page: [https://www.postgresql.org/ftp/odbc/versions/msi/](https://www.postgresql.org/ftp/odbc/versions/msi/)
2.  Download the latest installer that matches your system architecture (usually **x64** for 64-bit Windows).
3.  Run the downloaded `.msi` file and follow the on-screen installation steps.
4.  Restart KiCad after the installation is complete.

---
### **Linux**
For Linux, you can install the driver using your distribution's package manager.

* **For Debian-based systems (Ubuntu, Mint, etc.):**
    ```bash
    sudo apt update
    sudo apt install odbc-postgresql
    ```

* **For Red Hat-based systems (Fedora, CentOS, etc.):**
    * On modern Fedora:
        ```bash
        sudo dnf install postgresql-odbc
        ```
    * On older CentOS/RHEL:
        ```bash
        sudo yum install postgresql-odbc
        ```
* Restart KiCad after the installation is complete.

### Integration with KiCad

1.  **Clone this repository** to a stable location on your local machine:
    ```bash
    git clone [https://github.com/TektraSense/TektraSense-KiCad-DBLibs.git](https://github.com/TektraSense/TektraSense-KiCad-DBLibs.git)
    ```

2.  **Open KiCad** and go to `Preferences` > `Configure Paths...`.
    -   It is highly recommended to add a new environment variable, e.g., `TEKTRASENSE_LIBS`, pointing to the cloned directory (e.g., `/path/to/TektraSense-KiCad-DBLibs`). This makes your project paths portable.

3.  **Add the Symbol and Footprint Libraries:**
    -   Go to `Preferences` > `Manage Symbol Libraries...` and `Preferences` > `Manage Footprint Libraries...`.
    -   Add the `.kicad_sym` and `.kicad_mod` libraries from this repository, giving them descriptive **Nicknames** (e.g., `Tektra_Device`, `Tektra_Resistor_SMD`).

4.  **Add the Database Library:**
    -   Go to `Preferences` > `Manage Symbol Libraries...`.
    -   Click the `+` icon and select the `.kicad_dbl` file located in this repository.
    -   Ensure the database connection details within the `.kicad_dbl` file are correctly configured for your system.

---

## 🤝 Contributing

Contributions are managed internally by the TektraSense hardware team. Please follow the established workflow for adding, verifying, and committing new library assets.
