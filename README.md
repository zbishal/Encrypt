Encryptor - Simple Encryptor App
Created by Bishal | Version 2025.v1

Project Description
This Python-based application offers a straightforward approach to text encryption and decryption through an intuitive graphical interface built with Tkinter. At its core, it uses a reversible encoding scheme that secures user input by embedding a secret key within the text and applying Base64 encoding. The result is a simple yet effective way to protect sensitive information, accessible only to those who possess the correct key.

Functional Overview
Encryption & Decryption Logic
Encryption involves wrapping the plaintext with the user-defined key, placing it at both the beginning and end, and then encoding the entire string using Base64.

Decryption reverses this operation by decoding the Base64 string and verifying the key’s presence on both ends before extracting the original message.

This approach ensures that only users with the correct key can recover the original content, providing a basic layer of security against unauthorized access.

Key Validation
The application requires a non-empty key for both encryption and decryption operations.

During decryption, it confirms the key is present as both a prefix and suffix to validate the integrity of the data.

If the key does not match or the input data appears tampered with, the program alerts the user with an informative error message, preventing incorrect decryption attempts.

File Handling
Users can easily load plaintext or encrypted data from external .txt files using a convenient file dialog interface.

The imported content automatically populates the input text area, enabling efficient handling of larger texts or batch operations.

Logging Mechanism
A built-in console panel logs real-time feedback on the application’s status, including successful operations, word counts, and any errors encountered.

This feature improves transparency and assists users in tracking the progress and results of their actions.

Usage Instructions
Launch the application with Python 3.

Enter a secret key, which may be a string or numeric value, to be used for encryption or decryption.

Type in or import the text you wish to process.

Select Encrypt to secure your text or Decrypt to reveal the original content.

Review the output displayed in the designated area.

Consult the console log for detailed messages and any error notifications.

Licensing and Contribution
This project is open-source and freely available for anyone to use, modify, and distribute for personal, educational, or non-commercial purposes.
