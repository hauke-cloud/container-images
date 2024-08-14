# Container Images

![Build Status](https://img.shields.io/github/actions/workflow/status/hauke-cloud/container-images/build.yaml?branch=main)
![License](https://img.shields.io/github/license/hauke-cloud/container-images)
![Last Commit](https://img.shields.io/github/last-commit/hauke-cloud/container-images)
![Contributors](https://img.shields.io/github/contributors/hauke-cloud/container-images)

<p align="center">
  <img src="resources/readme/logo.png" alt="Repository Logo" width="400">
</p>

This repository contains all the necessary files and instructions
to build (Docker) container images used within the hauke.cloud ecosystem.

## Table of Contents

- [Introduction](#introduction)
- [Build Instructions](#build-instructions)
- [License](#license)
- [Contributing](#contributing)
- [Contact](#contact)

## Introduction

This repository provides a standardized way to build (Docker) images for
various applications and services. The images are optimized for
performance and security, and are designed to be easily
integrated into CI/CD pipelines.

## Build Instructions

To build a (Docker) image using this repository, follow the steps below:

1. **Clone the Repository**  
   Clone this repository to your local machine using the command:

   ```bash
   git clone https://github.com/hauke-cloud/container-images.git
   cd docker-image-builder
   ```

2. Build the Image  
   Run the following command to build the image:

   ```bash
   cd images/<image-name>
   docker build -t <image-name> .
   ```

3. Run the Image
  Run the following command to run the image:

   ```bash
   docker run -d <image-name>
   ```

## License

This Project is licensed under the GNU General Public License v3.0

- see the [LICENSE](LICENSE) file for details.

## Contributing

We welcome contributions from the community. Please follow these steps to contribute:

1. Fork this repository.
2. Create a new branch.
3. Make your changes.
4. Commit your changes.
5. Push to the branch.
6. Create a new Pull Request.

Contact us if you have any questions or need further information.

## Contact

For any inquiries or support requests, please open an issue in this
repository or contact us at [contact@hauke.cloud](mailto:contact@hauke.cloud).
