import tkinter as tk
from tkinter import ttk, filedialog, messagebox
import base64
#
# Created by Bishal | version 2025.v1
#
class Encryptor(tk.Tk):
    def __init__(self):
        super().__init__()
        self.title("Encrypt")
        self.geometry("600x800")
        self.minsize(500, 600)
        self.configure(bg="#f4f4f4")
        self.create_widgets()
        self.center_window()

    def center_window(self):
        self.update_idletasks()
        width, height = 600, 800
        x = (self.winfo_screenwidth() // 2) - (width // 2)
        y = (self.winfo_screenheight() // 2) - (height // 2)
        self.geometry(f"{width}x{height}+{x}+{y}")

    def create_widgets(self):
        self.grid_columnconfigure(0, weight=1)

        # I added the console to log messages, so you can see what’s happening. also it just looks cool, ngl.
        self.console = tk.Text(self, height=5, bg="#111", fg="#0f0", font=("Courier", 10))
        self.console.grid(row=0, column=0, sticky="nsew", padx=10, pady=(10, 0))
        self.log("Ready...")


        self.key_label = ttk.Label(self, text="Encryption Key:")
        self.key_label.grid(row=1, column=0, padx=10, pady=(20, 5), sticky="w")

        self.key_entry = ttk.Entry(self)
        self.key_entry.grid(row=2, column=0, padx=10, sticky="ew")
        

        # Umm, I didn’t test what types of keys you can use, but if you throw in random shit, it probably will crash… maybe. I’d just keep it simple..
        self.key_hint = ttk.Label(self, text="NOTE: Key is used to encode/decode the message. Keep it short but unique.", font=("Arial", 8), foreground="#666")
        self.key_hint.grid(row=3, column=0, padx=10, pady=(2, 15), sticky="w")


        self.input_label = ttk.Label(self, text="Input Text:")
        self.input_label.grid(row=4, column=0, padx=10, sticky="w")

        self.input_text = tk.Text(self, height=10)
        self.input_text.grid(row=5, column=0, padx=10, sticky="nsew")

        # Didn’t test the character limit, so go wild, lmfaoooooooo!
        self.output_label = ttk.Label(self, text="Output:")
        self.output_label.grid(row=6, column=0, padx=10, pady=(20, 0), sticky="w")

        self.output_text = tk.Text(self, height=10, state="disabled")
        self.output_text.grid(row=7, column=0, padx=10, sticky="nsew")


        button_frame = ttk.Frame(self)
        button_frame.grid(row=8, column=0, pady=20)
        button_frame.columnconfigure((0,1,2), weight=1)

        self.encrypt_btn = ttk.Button(button_frame, text="Encrypt", command=self.encrypt_text)
        self.encrypt_btn.grid(row=0, column=0, padx=5)

        self.decrypt_btn = ttk.Button(button_frame, text="Decrypt", command=self.decrypt_text)
        self.decrypt_btn.grid(row=0, column=1, padx=5)

        self.load_btn = ttk.Button(button_frame, text="Load File", command=self.load_file)
        self.load_btn.grid(row=0, column=2, padx=5)

        
        self.footer = ttk.Label(self, text="Created by Bishal | version 2025.v1", font=("Arial", 8), foreground="#999")
        self.footer.grid(row=9, column=0, pady=(0, 10))

        self.rowconfigure(5, weight=1)
        self.rowconfigure(7, weight=1)

    def log(self, msg):
        self.console.configure(state="normal")
        self.console.insert("end", f"{msg}\n")
        self.console.configure(state="disabled")
        self.console.see("end")

    def encrypt_text(self):
        key = self.key_entry.get()
        plain_text = self.input_text.get("1.0", "end").strip()

        if not key:
            self.log("Encryption aborted: missing key.")
            messagebox.showwarning("Missing Key", "Please enter an encryption key.")
            return

        if not plain_text:
            self.log("Encryption aborted: no input text.")
            return

        try:
            combined = f"{key}{plain_text}{key}".encode("utf-8")
            encrypted = base64.b64encode(combined).decode("utf-8")
            self.set_output(encrypted)
            self.log(f"Encrypted {len(plain_text.split())} words successfully.")
        except Exception as e:
            self.log(f"Encryption failed: {e}")

    def decrypt_text(self):
        key = self.key_entry.get()
        encrypted_text = self.input_text.get("1.0", "end").strip()

        if not key:
            self.log("Decryption aborted: missing key.")
            messagebox.showwarning("Missing Key", "Please enter the encryption key.")
            return

        if not encrypted_text:
            self.log("Decryption aborted: no input text.")
            return

        try:
            decoded = base64.b64decode(encrypted_text).decode("utf-8")
            if decoded.startswith(key) and decoded.endswith(key):
                decrypted = decoded[len(key):-len(key)]
                self.set_output(decrypted)
                self.log(f"Decrypted {len(decrypted.split())} words successfully.")
            else:
                self.log("Decryption failed: key mismatch.")
                messagebox.showerror("Decryption Error", "Invalid key or corrupted input.")
        except Exception as e:
            self.log(f"Decryption error: {e}")

    def load_file(self):
        file_path = filedialog.askopenfilename()
        if not file_path:
            return

        try:
            with open(file_path, "r", encoding="utf-8") as file:
                content = file.read()
                self.input_text.delete("1.0", "end")
                self.input_text.insert("1.0", content)
                self.log(f"Loaded file: {file_path.split('/')[-1]} ({len(content.split())} words)")
        except Exception as e:
            self.log(f"Failed to load file: {e}")

    def set_output(self, text):
        self.output_text.configure(state="normal")
        self.output_text.delete("1.0", "end")
        self.output_text.insert("1.0", text)
        self.output_text.configure(state="disabled")

if __name__ == "__main__":
    app = Encryptor()
    app.mainloop()
