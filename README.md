# 🧾 QR Code Generator (Django)

A simple Django-based application that generates and stores QR codes for website names using the `qrcode` and `Pillow` libraries. Each website name entered is converted into a QR code image and saved automatically.

## 📸 Features

- Accepts a website name as input.
- Generates a QR code for the input using the `qrcode` library.
- Saves the QR code as a 300x300 PNG image on a white canvas.
- Stores the image in the `qr_codes/` directory using Django's `ImageField`.
- Clean and extensible `save()` method that encapsulates the QR generation logic.

## 🛠 Technologies Used

- **Python 3**
- **Django**
- **Pillow (PIL)**
- **qrcode**

## 📁 Project Structure

```

qr\_code\_generator/
├── manage.py
├── db.sqlite3
├── qr\_code/
│   ├── models.py
│   ├── views.py
│   ├── templates/
│   └── static/
└── myenv/ (ignored)

````

## 📦 Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-username/qr-code-generator.git
   cd qr-code-generator
````

2. **Create and activate a virtual environment**:

   ```bash
   python -m venv myenv
   myenv\Scripts\activate  # On Windows
   ```

3. **Install dependencies**:

   ```bash
   pip install -r requirements.txt
   ```

4. **Run migrations**:

   ```bash
   python manage.py migrate
   ```

5. **Start the development server**:

   ```bash
   python manage.py runserver
   ```

6. Open your browser and visit:
   `http://127.0.0.1:8000/`

## 🧠 How It Works

The `Website` model in `models.py`:

* Accepts a name (string) field.
* Overrides the `save()` method to:

  * Generate a QR code image for the name.
  * Paste it on a white canvas (300x300).
  * Save the image in memory and upload it via Django’s file storage system.

## 📄 Example

When a user submits a name like `https://example.com`, a QR code is created and saved as:

```
qr_codes/qrcode-https://example.com.png
```

## 📂 .gitignore Example

```gitignore
__pycache__/
*.pyc
db.sqlite3
media/
myenv/
.env
```

## 📃 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more information.

---

**Made with ❤️ using Django**

```

---

Let me know if you'd like me to add a section for deployment (e.g., to PythonAnywhere or Render) or auto-generate a `requirements.txt` sample.
```
