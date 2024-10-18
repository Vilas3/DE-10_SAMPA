# DE-10_SAMPA

## Project Overview

This scientific initiation project focuses on the use of the DE10-Standard FPGA as a platform for the acquisition and filtering of particle physics data from the SAMPA chip. The SAMPA chip is specifically designed for the readout of data from particle detectors and is used in high-energy physics experiments. By leveraging the programmable logic capabilities of the DE10-Standard FPGA, this project aims to create a real-time system that processes and filters the data from the SAMPA chip for further analysis.

## Objectives

- **Data Acquisition:** Develop an interface between the DE10-Standard FPGA and the SAMPA chip to capture real-time particle physics data.
- **Data Filtering:** Implement signal processing algorithms on the FPGA to filter and clean the incoming data for more accurate analysis.
- **Linux-based Control System:** Utilize a Linux-based operating system for control and monitoring of the data acquisition process, running on the DE10-Standard's ARM processor.
- **Project Files:** Provide the necessary FPGA programming files (`.jic`) and Linux system image files (`.iso`) for replication and testing of the project.

## Project Components

- **FPGA Development Board:** The [DE10-Standard](https://www.terasic.com.tw/cgi-bin/page/archive.pl?Language=English&CategoryNo=165&No=1046) FPGA board from Terasic, equipped with an Intel Cyclone V SoC, serves as the main platform for this project.
- **SAMPA Chip:** A specialized chip designed for data acquisition from particle detectors, used in experiments like ALICE at CERN. It enables high-rate data acquisition in particle physics experiments.
- **Signal Processing Algorithms:** Filters are implemented using the FPGA logic to process incoming data from the SAMPA chip. These algorithms ensure that only the most relevant data is passed on for analysis.
- **Linux Operating System:** The control and communication software for this project runs on a custom Linux distribution, configured for the DE10-Standard's ARM core. This system manages the acquisition pipeline and handles data transfer.

## Repository Structure

- `/fpga/`: Contains FPGA-related files, including `.jic` programming files for the DE10-Standard board.
- `/linux/`: Contains Linux system images (`.iso`) that can be flashed to the DE10-Standard's SD card for system control and monitoring.
- `/docs/`: Includes technical documentation, schematics, and usage instructions for the project.
- `/scripts/`: Bash and Python scripts used for controlling the acquisition process and filtering configuration.

## Getting Started

### Prerequisites

To replicate and test this project, you will need the following:

- **Hardware:**
  - DE10-Standard FPGA board
  - SAMPA chip setup for data acquisition
  - SD card (8 GB or larger) for the Linux image
  - Host PC for development and FPGA programming

- **Software:**
  - Quartus Prime software for programming the FPGA
  - SD card flashing software (e.g., `dd` for Linux, Etcher for Windows/Mac)
  - A Linux machine or virtual machine for software development

### Installation

1. **FPGA Programming:**
   - Use Quartus Prime to load the `.jic` files onto the DE10-Standard FPGA.
   - The FPGA will be configured to interface with the SAMPA chip and start acquiring data.

2. **Linux Image Installation:**
   - Flash the provided Linux `.iso` image to an SD card using a tool such as `dd`:
     ```bash
     sudo dd if=path_to_image.iso of=/dev/sdX bs=4M status=progress
     ```
     Replace `/dev/sdX` with the actual device name of your SD card.
   - Insert the SD card into the DE10-Standard board and boot the system.

3. **Running the System:**
   - After booting the system, use the provided scripts to start the data acquisition and filtering process.
   - Monitor data acquisition through the serial interface or network connection as specified in the documentation.

### Usage

Once the system is set up, data from the SAMPA chip can be captured and filtered by the FPGA. The Linux-based system provides monitoring and control via command-line tools or custom scripts.

Refer to the `/docs/` folder for more detailed instructions on how to configure the system, manage data streams, and analyze the filtered results.

## Contributing

This project is open to contributions from the scientific community. If you'd like to contribute, please fork this repository, make your changes, and submit a pull request. Contributions can include:

- Optimizations for FPGA data processing
- Improvements to the Linux control software
- Documentation enhancements
- Bug fixes

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

## Acknowledgments

This project is supported by the [Name of Supporting Institution] and contributes to ongoing research in particle physics data acquisition systems. Special thanks to the developers of the SAMPA chip and the ALICE experiment at CERN for their contributions to this field.
