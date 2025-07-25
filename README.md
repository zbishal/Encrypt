# Encryptor - Simple Encryptor App

**Created by Bishal | Version 2025.v1**

---

## About This Project

I built this simple Python app to help with encrypting and decrypting text using a secret key. It uses Tkinter for the interface, so it’s easy to use even if you’re not a coder. The way it works is by wrapping your text with a key you provide, then encoding it with Base64. Only the right key can unlock the original message.

---

## How It Works

### Encryption & Decryption

- When you encrypt something, I take your text and add the key at the start and end, then convert it into Base64.
- To decrypt, the app decodes the Base64 string and checks that the key is at both ends before giving you the original text back.
- This way, if you don’t have the right key, you won’t be able to see the original message.

### Key Checks

- You have to enter a key — it can be any string or number — before encrypting or decrypting.
- If the key doesn’t match during decryption, the app will tell you something went wrong, so you don’t get incorrect output.

### Loading Files

- You can also open `.txt` files with your text or encrypted data.
- The app will load that text into the input box, so you don’t have to copy and paste manually.

### Logs and Feedback

- There’s a console area that shows you messages about what’s happening — like when something worked, how many words were processed, or if there was an error.
- This helps you keep track of what’s going on while you use the app.

---

## How To Use It

1. Run the program with Python 3.
2. Type in your secret key (anything you want).
3. Enter or load the text you want to encrypt or decrypt.
4. Click **Encrypt** to lock your text or **Decrypt** to unlock it.
5. Check the output area to see the result.
6. Watch the console for helpful messages or errors.

---

## License and Sharing

Feel free to use, change, or share this project however you want — for personal use, learning, or non-commercial. I’d appreciate a shoutout if you like, but it’s totally up to you.

---


## GUI:

<img width="614" height="843" alt="image" src="https://github.com/user-attachments/assets/2fe2cc93-518c-4418-ad44-b96bb862003a" />
