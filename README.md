# CAPTCHA Generator

A Python desktop application that generates random 5-7 character CAPTCHA codes and displays them as images in a Tkinter interface.

## Features

- Random letters and numbers generated with Python's `secrets` module
- Selectable length of 5, 6, 7, or random
- CAPTCHA image generation using `captcha.image.ImageCaptcha`
- Image display using Pillow and Tkinter
- Refresh and save-as-PNG actions
- Input validation and user-friendly error messages
- Tested service layer separated from the GUI

## Run locally

```bash
python -m venv .venv
# Windows: .venv\Scripts\activate
# macOS/Linux: source .venv/bin/activate
pip install -r requirements.txt
python app.py
```

## Run tests

```bash
pip install -r requirements-dev.txt
pytest -q
```

## Project structure

```text
app.py                    Tkinter user interface
captcha_service.py        Generation and file-saving logic
tests/                    Automated tests
generated_captchas/       Default output folder
```

## Interview explanation

The GUI collects the desired length and calls a separate service function. The service generates a random string, passes it to `ImageCaptcha`, and returns PNG bytes. Pillow converts those bytes into an image Tkinter can display. Keeping the service separate makes the logic easier to test and reuse.

