#  AI Travel Planner

<div align="center">

![Python](https://img.shields.io/badge/Python-3.8%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Tkinter](https://img.shields.io/badge/Tkinter-GUI-FF6F00?style=for-the-badge&logo=python&logoColor=white)
![ReportLab](https://img.shields.io/badge/ReportLab-PDF%20Export-CC0000?style=for-the-badge)
![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey?style=for-the-badge)
[![ML-Inside](https://img.shields.io/badge/AI--Powered-Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
<br/>

> **A fully offline Python desktop app that generates personalised day-by-day heritage travel itineraries for India — with PDF export and HTML share in one click.**
---
<img width="1919" height="1095" alt="image" src="https://github.com/user-attachments/assets/17369d1b-9ffc-43c4-881b-ba5af14f25c8" />


## 📸 Screenshots

| Planning Form | Generated Itinerary | PDF Export |
|:---:|:---:|:---:|
| Choose destination, budget, duration & interests | Day-by-day collapsible cards with time slots | Styled A4 PDF with gold heritage theme |

</div>

---

##  Features

-  **19 Heritage Destinations** across North, South, East, West & Central India
-  **AI-style Itinerary Generation** with animated loading sequence
-  **Morning / Afternoon / Evening** time slots for every day
-  **Flexible Trip Duration** — 2, 3, 5, 7 or 10 days
-  **Three Budget Tiers** — Budget, Mid-range, and Luxury with cost estimates
-  **Travel Styles** — Relaxed, Packed, Focused, or Flexible
-  **Interest Tags** — History, Architecture, Food, Photography, Culture, Adventure & more
-  **Traveller Types** — Solo, Couple, Family, or Group
-  **Real PDF Export** — Download a fully styled A4 PDF powered by ReportLab
-  **HTML Share Link** — Generate a standalone shareable web page, opens in browser
-  **Collapsible Day Cards** — Accordion-style breakdown with tags per activity

---

##  Destinations

| Region | Cities |
|:---|:---|
| 🏔️ **North India** | Agra, Delhi, Varanasi, Lucknow, Amritsar |
| 🌸 **Rajasthan** | Jaipur, Jodhpur, Udaipur, Jaisalmer |
| 🌴 **South India** | Hampi, Thanjavur, Madurai, Mysore |
| 🌊 **West India** | Mumbai, Ajanta & Ellora |
| 🏛️ **East & Central India** | Khajuraho, Sanchi, Bhubaneswar |

> Full itinerary data is included for **Agra, Delhi, Jaipur, Hampi and Varanasi**.  
> All other destinations use a smart default heritage template.

---

##  Getting Started

### Prerequisites

- Python **3.8 or higher**
- pip

### 1. Clone the repository

```bash
git clone 
cd Travel-Planner
```

### 2. Install dependencies

```bash
pip install reportlab
pip install scikit-learn
pip install numpy
pip install pandas
```

>  **Tkinter** is built into Python on Windows and macOS.  
> On Linux, install it separately:
> ```bash
> sudo apt-get install python3-tk
> ```

### 3. Run the app

```bash
python travel.py
```

---

##  How to Use

### Step-by-step

| Step | Action |
|:---:|:---|
| 1 | Select a **destination** from the dropdown |
| 2 | Choose **trip duration** — 2, 3, 5, 7, or 10 days |
| 3 | Pick your **budget** — Budget / Mid / Luxury |
| 4 | Toggle your **interests** — History, Food, Photography etc. |
| 5 | Choose a **travel style** — Relaxed, Packed, Focused, Flexible |
| 6 | Select **traveller type** — Solo, Couple, Family, Group |
| 7 | Click **"Generate AI Itinerary"** and see your plan |

<img width="718" height="729" alt="image" src="https://github.com/user-attachments/assets/a0e8323c-23ac-427a-ac66-e8ee59560761" />
<img width="698" height="338" alt="image" src="https://github.com/user-attachments/assets/3165b116-a469-40d9-b1c0-9401a3b1dc41" />


### Export & Share

| Button | What it does |
|:---|:---|
|  **Download PDF** | Opens a Save dialog → generates a styled A4 PDF → option to open immediately |
|  **Share Link** | Generates a standalone HTML file → opens in browser → copy path to share |
|  **Save** | Bookmarks the itinerary (extend with a database to persist) |

<img width="575" height="99" alt="image" src="https://github.com/user-attachments/assets/254e2894-a3f9-475e-8545-8d577c76feed" />

---

##  Tech Stack

| Technology | Role |
|:---|:---|
| **Python 3.8+** | Core application language |
| **Tkinter** | Native desktop GUI (no install needed) |
| **ttk.Combobox** | Styled dropdown for destination selection |
| **ReportLab** | PDF generation with custom A4 layout and gold styling |
| **threading** | Background loading animation without freezing the UI |
| **webbrowser** | Opens the HTML share page in the default browser |
| **tempfile** | Creates the temporary HTML share file |
| **filedialog** | Native Save As dialog for PDF export |
 
  **Recommendation Engine (KNN):** Implements a K-Nearest Neighbors model with Cosine Similarity. It maps a 10-dimensional user interest vector (History, Nature, Food, etc.) against a city-interest matrix to find the mathematically closest destination match.
- **Budget Predictor (Linear Regression):** Uses a Supervised Learning model trained on seasonal datasets. It predicts daily expenses by analyzing the relationship between trip duration, month of travel, and selected luxury tier.
- **NLP Intent Extraction:** A custom rule-based Natural Language Processing module. It uses regex tokenization and lexicon mapping to clean free-text input and extract specific city entities and travel intents.
<img width="1080" height="631" alt="image" src="https://github.com/user-attachments/assets/074f100b-6a68-4aa8-ac35-bf4dd0ebbd73" />


---

## 📁 Project Structure

```
Travel-Planner/
│
├── travel.py       # Entire application — single file
├── requirements.txt        # Python dependencies
└── README.md               # Project documentation
```

### Inside `travel.py`

```
travel.py
│
├── 🎨  COLOUR PALETTE          — UI hex constants (dark gold theme)
├── 🗃️  DESTINATION_DATA        — Full day/slot data for 5 cities
├── 📋  DESTINATIONS_LIST       — All 19 cities for the dropdown
│
├── 📄  generate_pdf()          — Builds styled A4 PDF with ReportLab
├── 🌐  generate_share_html()   — Builds standalone HTML share page
│
└── 🖥️  TravelPlannerApp        — Main Tkinter application class
    ├── _build_hero()           — Title & badge section
    ├── _build_form()           — Left panel: all form controls
    ├── _build_empty_state()    — Placeholder before generation
    ├── _show_loading()         — Animated loading screen
    ├── _on_generate()          — Triggers itinerary build in thread
    ├── _build_itinerary()      — Right panel: day cards & header
    ├── _build_slot()           — Morning / Afternoon / Evening slot
    ├── _download_pdf()         — PDF export handler
    └── _share_link()           — HTML share handler + dialog
```

---

## 📄 PDF Output

The exported PDF includes:

- **Brand header** — "" with gold divider
- **Journey title** — City name and tagline
- **Trip badges** — Days count, Budget tier, Travel pace
- **Stats bar** — Total days · Experiences · Monuments · Est. cost/day
- **Day cards** — Each day with Morning (7 AM), Afternoon (1 PM), Evening (6 PM)
- **Activity details** — Name, description, and interest tags
- **Footer** — Auto-generated timestamp
- 
<img width="805" height="927" alt="image" src="https://github.com/user-attachments/assets/3765beb6-4305-4d29-a5e4-d2ab0fa100d6" />

---

## 🌐 HTML Share Page

The Share Link feature generates a **fully self-contained `.html` file**:

- Same dark gold visual theme as the desktop app
- Responsive — works on mobile and desktop browsers
- **100% offline** — all data embedded, no internet needed
- Can be emailed, uploaded, or shared as a file link

<img width="940" height="454" alt="image" src="https://github.com/user-attachments/assets/5f988363-378d-457b-8071-f7e95cff77f5" />

---

## ⚙️ VS Code Users

If you see Pylance warnings like `"reportlab could not be resolved from source"` — **ignore them**. These are cosmetic type-checking warnings, not errors. The package is installed and the app runs fine.

To suppress them permanently, add to `.vscode/settings.json`:

```json
{
  "python.analysis.diagnosticSeverityOverrides": {
    "reportMissingModuleSource": "none"
  }
}
```

---

## 📦 requirements.txt

```
reportlab>=4.0.0
```

---

### Ideas for future improvements

- [ ] Real AI API integration (OpenAI / Gemini / Claude) for dynamic generation
- [ ] SQLite database to save and reload itineraries
- [ ] Google Maps integration showing monument locations
- [ ] Hotel & restaurant recommendations per budget tier
- [ ] International heritage destinations
- [ ] Light / dark theme toggle
- [ ] Export to `.ics` Google Calendar format
- [ ] Multi-language support
