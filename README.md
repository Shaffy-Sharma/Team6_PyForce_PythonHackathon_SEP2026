# 🏥 Cardiac Failure Lab Data Cleaning Project
**Team 6 - PyForce Python Hackathon (September 2026)**

---

## 📋 Table of Contents
1. [What Does This Project Do?](#what-does-this-project-do)
2. [Getting Started (Easy Setup)](#getting-started-easy-setup)
3. [System Requirements](#system-requirements)
4. [Step-by-Step Installation](#step-by-step-installation)
5. [How to Run the Project](#how-to-run-the-project)
6. [What Each Section Does](#what-each-section-does)
7. [Understanding the Output](#understanding-the-output)
8. [File Structure](#file-structure)
9. [Troubleshooting Guide](#troubleshooting-guide)
10. [Team Information](#team-information)

---

## 🎯 What Does This Project Do?

This project **cleans and validates cardiac failure patient lab data** to make it ready for medical analysis and research. Think of it like a data janitor that:

- ✅ Detects and removes duplicate patient records
- ✅ Finds and removes empty/useless columns
- ✅ Checks vital signs for unrealistic values (e.g., body temperature 150°C)
- ✅ Reports missing values and patterns
- ✅ Validates medical data logic (e.g., systolic BP should be higher than diastolic)
- ✅ Standardizes column names for consistency
- ✅ Saves a clean, validated dataset ready for analysis

**Input:** Raw lab data with inconsistencies and errors  
**Output:** Clean, validated lab data saved as `labs_cleaned.csv`

---

## 🚀 Getting Started (Easy Setup)

### What You Need Installed:
1. **Python 3.7 or higher** (free download from python.org)
2. **Jupyter Notebook** or **VS Code** with Python extension
3. **Git** (optional, for cloning the project)

### Quick Check - Do You Have Python?
Open your terminal/command prompt and type:
```bash
python --version
```
If you see a version number (like `Python 3.9.5`), you're good! If not, install Python.

---

## 🔧 System Requirements

| Requirement | What You Need |
|---|---|
| **Operating System** | Windows, macOS, or Linux |
| **Python Version** | 3.7 or higher (3.9+ recommended) |
| **RAM** | At least 2GB (4GB+ recommended) |
| **Disk Space** | ~500MB for Python and libraries |
| **Internet Connection** | Yes (only for initial setup) |

---

## 📥 Step-by-Step Installation

### Step 1️⃣: Download the Project
```bash
# Option A: Using Git (if you have it installed)
git clone <repository-url>
cd Team6_PyForce_PythonHackathon_SEP2026

# Option B: Download as ZIP
# 1. Click "Code" → "Download ZIP"
# 2. Extract the ZIP file
# 3. Open terminal in the extracted folder
```

### Step 2️⃣: Install Required Python Libraries

**On Windows:**
```bash
pip install pandas numpy jupyter
```

**On macOS/Linux:**
```bash
pip3 install pandas numpy jupyter
```

**What are these libraries?**
- `pandas`: For working with data tables (like Excel)
- `numpy`: For mathematical operations
- `jupyter`: For running interactive notebooks

### Step 3️⃣: Verify Installation
```bash
# Check if libraries are installed
python -c "import pandas; import numpy; print('✅ All libraries installed!')"
```

---

## ▶️ How to Run the Project

### Option A: Using Jupyter Notebook (Recommended for Beginners)

**Step 1: Start Jupyter Server**
```bash
# Navigate to project folder first (cd path/to/project)
jupyter notebook
```
This opens a browser window showing your project files.

**Step 2: Open the Notebook**
- Click on `Team6_Lab_cleaning.ipynb`
- You'll see the notebook with all the code and explanations

**Step 3: Run Each Section**
- Click on the first cell (code box)
- Press `Shift + Enter` to run it
- You'll see the results below
- Move to the next cell and repeat

**💡 Tip:** Run cells from top to bottom - they depend on each other!

---

### Option B: Using VS Code (With Python Extension)

**Step 1: Open the Project**
```bash
code .
```

**Step 2: Install Python Extension**
- Click Extensions (left sidebar)
- Search for "Python"
- Click "Install" on the Microsoft Python extension

**Step 3: Open the Notebook File**
- Click `Team6_Lab_cleaning.ipynb` in the file explorer
- VS Code will show it as an interactive notebook

**Step 4: Run the Cells**
- Click the ▶️ button on each cell to run it
- Or select a cell and press `Shift + Enter`

---

### Option C: Using Command Line (For Advanced Users)
```bash
# Navigate to project folder
cd Team6_PyForce_PythonHackathon_SEP2026

# Run with this command (processes all cells)
jupyter nbconvert --to notebook --execute Team6_Lab_cleaning.ipynb
```

---

## 🔍 What Each Section Does

### **Section 1: Load the Dataset**
- **What it does:** Opens the main CSV file with raw lab data
- **Input file:** `data/cardiac_failure/labs.csv`
- **Output:** Displays the shape (rows and columns) of data
- **Why it matters:** Confirms data is loaded and shows initial size

---

### **Section 2: Initial Data Inspection**
- **What it does:** Shows first/last 5 rows, column names, and data dimensions
- **Output:** Preview of your data structure
- **Why it matters:** Understand what you're working with before cleaning

---

### **Section 3: Check for Duplicate Rows**
- **What it does:** Finds duplicate patient records (same data repeated)
- **Output:** Count of exact duplicates found
- **Why it matters:** Duplicates skew medical statistics

---

### **Section 4: Find 100% Empty Columns**
- **What it does:** Identifies columns where EVERY value is missing/empty
- **Output:** List of useless columns to remove
- **Why it matters:** Empty columns add no information and waste storage

---

### **Section 5: Drop Empty Columns**
- **What it does:** Removes the empty columns found in Section 4
- **Output:** Confirmation of deleted columns
- **Why it matters:** Cleaned dataset is smaller and faster to process

---

### **Section 6: Validate Body Temperature**
- **What it does:** Checks if temperature readings are medically realistic
- **Normal range:** 35°C to 42°C (any value outside is concerning)
- **Output:** Reports extreme temperatures and suspicious values
- **Why it matters:** Catches data entry errors (e.g., "450°C" instead of "45.0°C")

---

### **Section 7: Missing Values Analysis**
- **What it does:** Creates a report showing which columns have missing data
- **Output:** Percentage of missing data per column (sorted high to low)
- **Saves:** `missing_values_report.csv`
- **Why it matters:** Helps decide if a column is reliable (70% missing? Unreliable!)

---

### **Section 8: Check Data Types**
- **What it does:** Verifies each column stores the right data type
  - Numbers should be stored as "float64" or "int64"
  - Text should be stored as "object"
- **Output:** Shows each column and its data type
- **Why it matters:** Type mismatches cause calculation errors

---

### **Section 9: Detect Data Type Mismatches**
- **What it does:** Finds columns storing numbers as text (or vice versa)
- **Example:** A phone number stored as a number instead of text
- **Output:** Reports of problematic columns
- **Why it matters:** Prevents errors in mathematical operations

---

### **Section 10: Summary Statistics**
- **What it does:** Shows min, max, and average values for each numeric column
- **Output:** Table with statistics for vital signs and lab values
- **Why it matters:** Quick overview of data ranges and plausibility

---

### **Section 11: Inspect Zero Values**
- **What it does:** Counts how many times each column has a zero value
- **Output:** List of columns with zeros and their percentages
- **Why it matters:** A systolic BP of 0 is impossible - indicates missing/error data

---

### **Section 12: Standardize Column Names**
- **What it does:** Renames `inpatient_number` to `patient_id` for consistency
- **Output:** Confirmation of renamed column
- **Why it matters:** Different naming conventions cause confusion

---

### **Section 13: Validate Blood Pressure Logic**
- **What it does:** Checks if systolic BP > diastolic BP (true for valid readings)
- **Output:** Count of rows where this logic fails
- **Why it matters:** Catches reversed or swapped BP readings

---

### **Section 14: Check for Negative Values**
- **What it does:** Finds any negative numbers in columns that should be positive
- **Example:** A negative heart rate is impossible
- **Output:** List of problematic columns
- **Why it matters:** Negative values are data errors

---

### **Section 15: Save Cleaned Data**
- **What it does:** Exports the cleaned dataset to a CSV file
- **Output file:** `data/cleaned/labs_cleaned.csv`
- **Why it matters:** This is your final, ready-to-use dataset

---

### **Section 16: Check Vital Signs at Zero**
- **What it does:** Identifies patient records where vital signs are exactly 0
- **Vital signs checked:** Systolic BP, diastolic BP, MAP, pulse, respiration
- **Output:** Table showing these suspicious records
- **Why it matters:** Zero vital signs usually mean data is missing or corrupted

---

### **Section 17: Round MAP Value**
- **What it does:** Rounds the MAP (Mean Arterial Pressure) to 2 decimal places
- **Output:** Verification of rounding
- **Why it matters:** Standardizes precision for consistency

---

## 📊 Understanding the Output

When you run the notebook, you'll see outputs like:

```
1. Initial dataset loaded successfully. Shape: (1000, 15)
```
**Translation:** 1,000 patient records with 15 pieces of information per patient

```
Total duplicate rows found: 5
```
**Translation:** Found 5 exact copies of existing records - should be removed

```
⚠️ Readings above 42°C: 3
```
**Translation:** 3 patients have impossible body temperatures - needs investigation

```
✅ Clean! No negative values found in any numeric columns.
```
**Translation:** Good news! No obviously wrong data here.

---

## 📁 File Structure

```
Team6_PyForce_PythonHackathon_SEP2026/
│
├── 📄 README.md                          👈 You are here!
├── 📔 Team6_Lab_cleaning.ipynb           ← Main notebook (run this)
│
├── 📁 data/
│   ├── 📁 cardiac_failure/               ← Raw data folder
│   │   ├── labs.csv                      ← Main lab data (input)
│   │   ├── cardiac_complications.csv
│   │   ├── demography.csv
│   │   ├── hospitalization_discharge.csv
│   │   ├── patient_prescriptions.csv
│   │   ├── patienthistory.csv
│   │   └── responsiveness.csv
│   │
│   └── 📁 cleaned/                       ← Cleaned data folder
│       └── labs_cleaned.csv              ← Output (clean data)
│
└── 📄 missing_values_report.csv          ← Generated report (shows missing data)
```

---

## 🐛 Troubleshooting Guide

### Problem 1: "ModuleNotFoundError: No module named 'pandas'"

**Cause:** Python libraries not installed

**Fix:**
```bash
# Windows
pip install pandas numpy jupyter

# macOS/Linux
pip3 install pandas numpy jupyter
```

Then restart Jupyter and try again.

---

### Problem 2: "FileNotFoundError: data/cardiac_failure/labs.csv"

**Cause:** Wrong folder location or file path

**Fix:**
1. Make sure you're in the project folder containing `README.md`
2. Check the `data/cardiac_failure/` folder exists
3. Run this command to verify:
   ```bash
   ls data/cardiac_failure/
   ```
   Should show the CSV files

---

### Problem 3: "NameError: name 'data' is not defined"

**Cause:** Ran cells out of order or skipped Section 1

**Fix:**
1. Go back to Section 1 (Load the Dataset)
2. Click ▶️ or press `Shift + Enter` to run it
3. Then run the other sections in order

**💡 Important:** Always run cells from top to bottom!

---

### Problem 4: Jupyter Won't Stop Running (Spinning Circle)

**Cause:** Processing takes too long (usually 30 seconds or less)

**Fix:**
- Wait 1-2 minutes for it to complete
- If it's still spinning after 5 minutes, press the ⏹️ **Stop** button (square icon)
- Restart the kernel: Click **Kernel** → **Restart**

---

### Problem 5: Command Not Found: `python` or `pip`

**Cause:** Python not installed or not in system PATH

**Fix:**
1. **Windows:** Reinstall Python, check "Add Python to PATH"
2. **macOS:** Use `python3` and `pip3` instead
   ```bash
   python3 --version
   pip3 install pandas
   ```

---

### Problem 6: Permission Denied When Saving Output

**Cause:** Folder doesn't exist or no write permission

**Fix:**
```bash
# Create the cleaned folder if it doesn't exist
mkdir -p data/cleaned

# Grant folder permissions (macOS/Linux)
chmod 755 data/cleaned
```

---

### Problem 7: Notebook Shows Empty Cells

**Cause:** Jupyter isn't displaying content properly

**Fix:**
1. Refresh the browser (`Cmd+R` on Mac, `Ctrl+R` on Windows)
2. Restart Jupyter:
   ```bash
   # Press Ctrl+C in terminal to stop
   # Then restart
   jupyter notebook
   ```

---

## 💡 Tips for Success

1. **Run one cell at a time** - Press Shift+Enter after each cell
2. **Read the output** - It tells you what's happening
3. **Don't skip sections** - They build on each other
4. **Check the data folder** - Make sure input CSV files exist
5. **Keep the notebook open** - Closing it loses your progress
6. **Look for red text** - It usually means an error occurred

---

## 👥 Team Information

- **Team Name:** PyForce
- **Project:** Cardiac Failure Lab Data Cleaning
- **Event:** Python Hackathon - September 2026
- **Team Members:** Team 6

---

## 📝 What's Next After Cleaning?

Once you have `labs_cleaned.csv`, the clean data can be used for:
- Statistical analysis of cardiac failure
- Machine learning predictions
- Medical research papers
- Hospital dashboards and reports
- Pattern identification in patient health

---

## 🆘 Need Help?

If you encounter issues not listed here:

1. **Check the error message carefully** - It often tells you what's wrong
2. **Google the error** - Usually someone else had the same problem
3. **Try restarting** - Close and reopen Jupyter/VS Code
4. **Check Python version** - Run `python --version` (should be 3.7+)
5. **Reinstall libraries** - Run `pip install --upgrade pandas numpy jupyter`

---

## 📄 License & Attribution

This project is part of the Team 6 submission for the PyForce Python Hackathon (September 2026).

---

**Happy data cleaning! 🎉**
