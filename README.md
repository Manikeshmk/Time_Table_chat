# 📅 Intelligent Timetable & Schedule Automator
> **Transforming messy spreadsheets into queryable intelligence.**

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)

---

## 💡 The Problem We Solved

### ⚠️ The Challenge: "The Non-Standard Grid"
Most institutional timetables are designed for human eyes, not machines. This creates a "Data Desert" for automation:
*   **🧩 Merged Cells:** Visual blocks that hide data from standard CSV parsers.
*   **🕳️ Irregular Gaps:** Breaks and transitions that confuse linear search.
*   **🎭 Complex Baskets:** Overlapping elective slots that require contextual filtering.

### ✅ Our Solution
We built an **automated coordinate-mapping engine**. By reading the underlying XML structure of the spreadsheet, our tool "re-hydrates" every individual cell, ensuring 100% data continuity across merged ranges.

---

## 🛠️ Tech Stack & Objects

*   **🐍 Python 3.12:** The backbone of the logic engine.
*   **🐼 Pandas:** High-performance indexing for the coordinate system.
*   **🔓 Openpyxl:** Deep-meta parsing to decode merged cell boundaries.
*   **🧪 Regex (re):** Pattern matching for natural language time extraction.
*   **🌐 Requests:** Real-time cloud synchronization with remote sources.

---

## ⚙️ Core Logic

| Phase | Object | Description |
| :--- | :---: | :--- |
| **Boundary Detection** | 📍 | Identifies grid anchors using keywords like `Time` and `Day`. |
| **Cell Hydration** | 💧 | Clones values from lead cells into all secondary merged coordinates. |
| **Temporal Parsing** | 🕰️ | Translates "tomorrow" or "10:45" into machine-readable calendar objects. |
| **Smart Consolidation** | 🔗 | Merges consecutive 15/30-min segments into single human blocks. |

---

## 🚀 Key Advantages

*   **✨ Zero Manual Entry:** Syncs directly via live URL.
*   **🧠 Context Awareness:** Automatically identifies "today" vs "tomorrow" using system clocks.
*   **🛡️ Gap Preservation:** Smart enough to know the difference between a merged lecture and a free period.
*   **💬 Human-Centric Output:** No column letters or row numbers—just clean times and subjects.

---

## 📖 Usage Examples
```python
# 📅 Get your full consolidated schedule for the day
assistant("What classes do I have today?")

# 🔍 Find every instance of a specific course
assistant("When is the Data Security session?")

# ⏱️ Check a specific time-window
assistant("Today 12:15 class")
