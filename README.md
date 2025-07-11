# Chain of Custody OTA Protocol - ProVerif Analysis

This repository contains the ProVerif models for the security analysis of a Chain of Custody protocol for Over-the-Air (OTA) updates.

This work was developed as a university project for the "Security verification and testing" (02TYAUV) exam at Politecnico di Torino, held by Professor Riccardo Sisto. The project was graded 30/30 cum laude.

## Project Overview

The main objective of this project is to formally verify the security properties of the protocol described in the `OTA_Protocol.pdf` document. The analysis is conducted using the ProVerif cryptographic protocol verifier.

The verification focuses on two main phases of the protocol:
1.  **Device Onboarding**: The initial process of registering a new device in a secure manner.
2.  **Secure Update**: The procedure for securely delivering and applying updates to the device.

The analysis also explores a version of the protocol enhanced with **Perfect Forward Secrecy (PFS)** to provide stronger security guarantees.

## Repository Structure

The repository is organized as follows:

-   `onboarding.pv`: ProVerif model for the device onboarding phase.
-   `secureUpdate.pv`: ProVerif model for the secure update phase.
-   `PFS/onboarding_PFS.pv`: ProVerif model for the onboarding phase, including Perfect Forward Secrecy.
-   `PFS/secureUpdate_PFS.pv`: ProVerif model for the secure update phase, including Perfect Forward Secrecy.
-   `OTA_Protocol.pdf`: The final report describing the protocol under analysis.


## How to Run the Analysis

To run the verification, you need to have [ProVerif](https://proverif.gitlab.io/) installed.

Once installed, you can run the analysis on each model using the following command in your terminal:

```sh
proverif <file_name.pv>
```

For example, to verify the onboarding model, run:
```sh
proverif onboarding.pv
```

## Security Queries

Each `.pv` file contains specific queries to verify security properties such as:
-   Confidentiality of sensitive data (e.g., passwords, serial numbers).
-   Authentication between the parties.
-   Session key secrecy and integrity.
-   Correctness of the protocol execution flow (injectivity).

The results of the analysis will be printed to the console by ProVerif.
