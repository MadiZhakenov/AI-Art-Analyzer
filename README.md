# AI Art Analyzer 🎨🤖

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT) <!-- You can choose another license -->
[![Python Version](https://img.shields.io/badge/Python-3.x-blue.svg)](https://www.python.org/) <!-- Specify your Python version -->

A Telegram bot powered by Google Gemini API, designed to analyze and interpret the emotional content of visual artworks.

**Author:** Madi Zhakenov (SE-2327), Astana IT University, 2025

---

## ✨ About The Project

Art perception is subjective, and not every viewer can easily interpret the emotions embedded by the artist. **AI Art Analyzer** is an intelligent tool developed to help users better understand the emotional message of artworks. The bot leverages the capabilities of the Google Gemini model to analyze visual elements (color, composition, texture, brushstroke style) and textual descriptions (if provided by the user), offering in-depth analysis and possible interpretations.

---

## 🖼️ Demo (Video Example)

https://youtube.com/shorts/U31Z49a0u_w?si=hZouxN2BOXjvrdAA

---

## 🚀 Key Features

*   **Image Analysis:** Identifies key visual elements (color palette, composition, brushstroke style, texture).
*   **Emotional Interpretation:** Detects and describes the emotions an artwork might evoke, offering multiple possible interpretations.
*   **Element Impact Explanation:** Clarifies how specific visual elements influence the emotional response.
*   **User Assumption Evaluation:** If the user shares their impressions, the bot first evaluates their accuracy.
*   **Textual Description Processing:** Considers textual descriptions or user comments to refine the analysis.
*   **Recommendations:** Suggests artworks with similar emotional content.
*   **Theoretical Foundation:** Analysis is based on research in art perception (influence of color, composition, texture).

---

## 🛠️ Technologies Used

*   **Python:** The primary programming language.
*   **Google Gemini API:** The core for image analysis and text generation (`gemini-2.0-flash-exp`).
*   **pyTelegramBotAPI (`telebot`):** Library for interacting with the Telegram API.

---

## ⚙️ Installation and Setup

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/MadiZhakenov/AI-Art-Analyzer.git
    cd AI-Art-Analyzer
    ```

2.  **Create and activate a virtual environment (recommended):**
    ```bash
    python -m venv venv
    # Windows
    venv\Scripts\activate
    # MacOS/Linux
    source venv/bin/activate
    ```

3.  **Install dependencies:**
    Create a `requirements.txt` file with the following content:
    ```txt
    google-generativeai
    pyTelegramBotAPI
    Pillow # Often implicitly required for image handling
    python-dotenv
    ```
    Then run:
    ```bash
    pip install -r requirements.txt
    ```

4.  **Configure API Keys:**
    *   **IMPORTANT:** Do not hardcode API keys directly in your code! Use environment variables or a configuration file (`.env`).
    *   Rename the `.env.example` file (if you create one) to `.env` and add your keys:
      ```dotenv
      TELEGRAM_BOT_TOKEN='YOUR_TELEGRAM_BOT_TOKEN'
      GEMINI_API_KEY='YOUR_GEMINI_API_KEY'
      ```
    *   Modify `AIAnalyzerBot.py` to read keys from environment variables:
      ```python
      import os
      from dotenv import load_dotenv # Requires python-dotenv

      load_dotenv() # Loads variables from .env file

      TELEGRAM_BOT_TOKEN = os.getenv('TELEGRAM_BOT_TOKEN')
      GEMINI_API_KEY = os.getenv('GEMINI_API_KEY')

      if not TELEGRAM_BOT_TOKEN or not GEMINI_API_KEY:
          raise ValueError("TELEGRAM_BOT_TOKEN and GEMINI_API_KEY must be set in environment variables or a .env file.")

      # ... rest of the code ...
      ```

5.  **Adapt File Paths:**
    *   **Recommendation:** Place the PDF files and initial images (`picture1.webp`, `picture2.jpeg`) in a folder within your project (e.g., `initial_data/`) and use relative paths in the code. Alternatively, if these files are only needed for the initial model setup (in `model.start_chat`), consider loading them once during setup rather than hardcoding paths.
    *   Modify the code to use relative paths:
      ```python
      # Example
      # files = [
      #   upload_to_gemini("initial_data/Цвета.pdf", mime_type="application/pdf"), # Keep original names if needed by Gemini
      #   # ... and so on ...
      # ]
      ```
    *   **Important:** Ensure these initial files (`Цвета.pdf`, `Стили мазок.pdf`, etc.) are added to your repository if they are essential for the bot's operation, especially for the initial chat history.

6.  **Run the bot:**
    ```bash
    python AIAnalyzerBot.py
    ```

---

## 📖 How to Use

1.  Find your bot on Telegram by its username (e.g., `@artanalyzer_bot` based on the screenshot, please verify the current username).
2.  Send the `/start` command to get the welcome message.
3.  Send an image (painting, drawing) to the bot.
4.  You can add a text caption to the image (e.g., your assumptions or the artwork's title). The bot will consider this text during analysis.
5.  The bot will provide a description of the artwork, an analysis of its emotional perception, possible interpretations, and other relevant information.

---

## ✅ Testing Results

Testing showed that the bot:

*   Correctly describes artworks, highlighting key visual elements.
*   Considers the subjectivity of perception by offering multiple interpretations.
*   Analyzes emotional aspects, explaining the influence of artistic elements.
*   Generates relevant recommendations for works with similar emotional content.

---

## 🔮 Future Development

*   Expanding functionality to analyze video materials and complex art objects.
*   Localization into other languages to increase the audience.
*   Integration into educational platforms, museums, and virtual galleries.

---

## 🤝 Contributing

Contributions are welcome! Please feel free to create Issues or Pull Requests.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE). <!-- Ensure you have a LICENSE file with the MIT license text in your repository -->

---

## 📞 Contact

Madi Zhakenov - [MadiZhakenov](https://github.com/MadiZhakenov)

---
