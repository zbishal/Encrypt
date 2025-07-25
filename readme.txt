# Encryptor

Created by Bishal | Version 2025.v1

---

## Project Description

This Python application implements a basic encryption and decryption tool using Tkinter for the graphical user interface. The core functionality centers around a reversible encoding scheme that wraps user input with a key and applies Base64 encoding, allowing for text confidentiality based on a user-defined secret key.

---

## Functional Overview

### Encryption & Decryption Logic

- **Encryption** is performed by concatenating the key as a prefix and suffix to the plaintext, then encoding the resultant string using Base64.
- **Decryption** reverses this process by Base64 decoding the input and removing the key from both ends, validating that the provided key matches the original used during encryption.
- This method ensures that only the correct key can retrieve the original plaintext, preventing unauthorized access.

### Key Validation

- The application enforces the presence of a non-empty key before any encryption or decryption operation.
- During decryption, the key is verified by checking its presence as both prefix and suffix in the decoded string.
- In case of key mismatch or corrupted input, an error message is triggered to inform the user of decryption failure.

### File Handling

- Users can import plaintext or encrypted data from external text files through a file dialog.
- Loaded content is injected into the input text area, facilitating batch or large text processing.

### Logging Mechanism

- A dedicated console area records operational status, including success messages, word counts, and error conditions.
- Logging aids in transparency and debugging by providing real-time feedback on performed actions.

---

## Usage Instructions

1. Launch the application with Python 3.
2. Enter a numeric or string key used for encryption/decryption.
3. Input or load the text to be processed.
4. Select either **Encrypt** or **Decrypt** based on intended operation.
5. Review the output area for results.
6. Monitor the console log for detailed status and potential errors.

---

## Licensing and Contribution

This project is freely available for anyone to use, modify, and distribute for personal, educational, or commercial purposes without restriction. Attribution to the original author (Bishal) is appreciated but not mandatory.

---

