# 📅 Intelligent Timetable & Schedule Automator

An advanced Python-based solution that transforms complex, non-standard institutional spreadsheets into an interactive, queryable AI assistant.

---

## 🛠️ Tech Stack

| Technology | Purpose |
| :--- | :--- |
| **Python 3.12** | Core programming logic |
| **Pandas** | High-performance data manipulation and filtering |
| **Openpyxl** | Spreadsheet metadata parsing & merged cell handling |
| **Regex (re)** | Natural language time and date extraction |
| **Requests** | Live cloud data synchronization |

---

## 💡 The Problem We Solved

### The Major Issue: "Non-Standard Grid Mess"
Most academic or corporate timetables are designed for human eyes, not machines. They use **merged cells** to show long lectures, **irregular gaps** to show breaks, and **overlapping slots** for elective "baskets." Standard CSV parsers fail here because:
1. They leave "holes" in the data where cells were merged.
2. They cannot correlate a specific time (e.g., 11:15 AM) if it falls in the middle of a 2-hour merged block.
3. Irregular naming conventions make standard search impossible.

### Our Solution
We built an **automated coordinate-mapping engine** that treats the spreadsheet like a database. By reading the Excel XML structure directly, we "re-hydrate" empty merged cells and standardize every minute of the day into a searchable grid.

---

## ⚙️ Core Logic

1.  **Metadata Extraction**: Instead of reading raw text, the script identifies the boundaries of the grid using anchor keywords (`Time`, `Day`).
2.  **Cell Normalization**: Uses `openpyxl` to detect `merged_cells` ranges. It clones the value from the lead cell to all "hidden" cells within the range, ensuring data continuity.
3.  **Intelligence Layer**: 
    *   **Temporal Parsing**: Converts queries like "tomorrow" or "15-08-2026" into calendar objects.
    *   **Range Validation**: If you ask for "11:00," the AI checks if that timestamp sits between the `start` and `end` times of any known session.
4.  **Consolidation Algorithm**: Intelligently merges consecutive identical slots into a single human-readable block (e.g., three 30-minute segments become one 90-minute entry).

---

## 🚀 Advantages

*   **Zero Manual Entry**: Syncs directly with a Google Sheets/Excel URL.
*   **Contextual Awareness**: Knows what day it is today and what "tomorrow" means without user input.
*   **Gap Preservation**: Distinguishes between a "merged cell" and a "free period" (Gap).
*   **Natural Language Support**: Ask for specific courses, specific times, or full-day summaries.

---

## 📖 How to Use
```python
# To see today's consolidated schedule
assistant("What classes do I have today?")

# To find a specific course
assistant("When is the Machine Learning session?")

# To check a specific time
assistant("Today 10:45 class")
