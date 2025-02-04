# 🎵 Audacity Label Generator

## 📌 Overview
This script generates **randomized label files** for use in **Audacity**, supporting both **percussive and ambient** soundscapes. It allows fine control over the **labeling density** and ensures **track length accuracy** by taking the duration as an argument.

## 🚀 Features
- **Percussive Mode**: Short, non-overlapping labels (1-3 sec)
- **Ambient Mode**: Long, overlapping labels (5 sec - 5 min)
- **Hybrid Mode**: Mix of percussive and ambient labels with customizable ratio
- **Manual Track Length Input**: Specify track duration in `mm:ss` format
- **Versioned Output**: Each label file has a timestamp to avoid overwriting
- **Command-line Help**: `--help` shows usage instructions
- **Auto Mode**: Generates a random command suggestion

---

## 🛠 Installation
### **Prerequisites**
- Python 3.x
- No external dependencies (FFmpeg **not required**)

### **Clone the Repository**
```sh
git clone https://github.com/YOUR_GITHUB_USERNAME/audacity-label-generator.git
cd audacity-label-generator
```

---

## 📖 Usage

### **Basic Syntax:**
```sh
python3 generate_labels.py "filename.wav" [mode] [track_length] [weight] [optional: split]
```
- **`filename.wav`**: The audio file you are labeling
- **`mode`**: `percussive`, `ambient`, or `hybrid`
- **`track_length`**: Specify duration in `mm:ss` (e.g., `35:22`)
- **`weight`**: A number (1-10) controlling label density
- **`split`** *(hybrid mode only)*: Two numbers (e.g., `70 30`) for percussive vs. ambient ratio

### **Examples:**
#### 1️⃣ **Percussive Mode (Short, Non-Overlapping Labels)**
```sh
python3 generate_labels.py "perc-chaos.wav" percussive 35:22 5
```
✅ Generates **short, dense labels** for a **35m22s track** with medium density.

#### 2️⃣ **Ambient Mode (Long, Overlapping Labels)**
```sh
python3 generate_labels.py "soundscape.wav" ambient 60:00 4
```
✅ Generates **long, overlapping labels** for a **60-minute track**.

#### 3️⃣ **Hybrid Mode (Mix of Percussive & Ambient Labels)**
```sh
python3 generate_labels.py "perc-chaos.wav" hybrid 33:40 70 30 6
```
✅ **70% percussive, 30% ambient labels** for a **33m40s track**, medium density.

#### 4️⃣ **Auto-Generate a Command**
```sh
python3 generate_labels.py auto
```
✅ Prints a **randomly generated command** for quick testing.

---

## 📂 Output
The script generates a **timestamped label file**:
```sh
labels_2025-02-04_perc-chaos_percussive_v141530.txt
```
Each file contains tab-separated label data:
```
10.5\t12.2\t2025-02-04_perc-chaos_2s_Early_L01
320.8\t323.0\t2025-02-04_perc-chaos_2.2s_Middle_L02
```

---

## 🔄 Importing Labels in Audacity
1. **Open Audacity** and load your **audio file**.
2. **Go to** `File > Import > Labels...`
3. **Select the generated `.txt` file**.
4. Click **Open** → A new label track appears.

⚠️ **To overwrite labels**, first **delete the old label track** (`Tracks > Remove Tracks`), then import the new file.

---

## 🌟 Contributing
Feel free to **fork the repo**, submit **pull requests**, or suggest features!

---

## 📜 License
This project is licensed under the **MIT License**.

---

## 📬 Contact
Created by **[YOUR NAME]**  
GitHub: [YOUR_GITHUB_PROFILE]  
Email: [YOUR_EMAIL]

