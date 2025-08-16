# 📘 Syracuse University iSchool OPT Research Task 05

This project analyzes how Syracuse University Men’s Football changed from **2021** to **2024** using season-level stats from the **first pages** of each year’s cumulative stats PDFs.

The workflow has two parts:

1. **🤖 LLM Q&A** — I asked ChatGPT (GPT-4 and GPT-5) focused questions using only the first-page numbers and recorded the **Model Output** (the model’s answer).  
2. **💻 Python Verification Notebook** — I verified each claim against **typed values** stored in two Python dictionaries (`season_2021` and `season_2024`) and added **descriptive stats** (W-L, Win% overall / conference / non-conference / home / away / neutral), plus simple charts.

> ⚠️ **Important**: The notebook does **not** parse PDFs or read external files. The input data is **typed manually** into two dictionaries at the top of the notebook. If your PDFs differ, update those dictionaries and re-run.

---

## 📦 What’s Included

- **LLM Q&A Analysis** — questions answered by ChatGPT (Model Output) and my **Verification** for each.  
- **Programmatic Verification** — `Task_05_Syracuse_Football.ipynb`:
  - recomputes differences,
  - prints **True/False** for each LLM claim,
  - shows **descriptive stats** (W-L and Win% splits),
  - and draws three quick `matplotlib` bar charts (yards/game, points/game, plays/game).
- **Transparency** — every number used is listed below and encoded in the notebook dictionaries.

---

## 🗂 Data Notes

- **Source**: Syracuse 2021 and 2024 cumulative stats PDFs (page 1 only).  
- **Scope**: yards/game, yards/play, total plays, points/game, third-down %, red-zone %, turnovers, sacks, penalties, attendance, and record splits.  
- **Input Method**: values typed into `season_2021` and `season_2024` dictionaries; **no file ingestion**.

### 📊 Key Typed Values (highlights)

**2021 (12 games)**  
- Record: **5–7** (Home 3–3, Away 2–4, Neutral 0–0)  
- Conference: **2–6** | Non-Conf: **3–1**  
- Offense: 366.5 yds/g (rush 213.5, pass 153.0), 5.7 yds/play, 778 plays (~64.8/g), 24.9 pts/g  
- 3rd down: 32.9% | TOP: 29:14  
- Red zone: 76.5% score, 58.8% TD  
- Turnovers: –5 margin  
- Sacks: 37 for / 32 allowed  
- Rush eff: 5.2 yds/rush (off), 3.5 yds/rush allowed (def)  
- Attendance: 32,461 avg (227,224 total)

**2024 (13 games)**  
- Record: **10–3** (Home 5–2, Away 4–1, Neutral 1–0)  
- Conference: **5–3** | Non-Conf: **5–0**  
- Offense: 467.6 yds/g (rush 97.6, pass 370.0), 6.1 yds/play, 1000 plays (~76.9/g), 34.1 pts/g  
- 3rd down: 49.0% | TOP: 33:04  
- Red zone: 85.5% score, 69.4% TD  
- Turnovers: +1 margin  
- Sacks: 27 for / 29 allowed  
- Rush eff: 3.2 yds/rush (off), 5.0 yds/rush allowed (def)  
- Attendance: 39,130 avg (273,913 total)

> If your PDFs show different values, change them here and in the notebook dicts.

---

## 🧠 LLM Q&A (Model Output + Verification)

### Q1 — Offensive identity shift
**Model Output**  
2021: 213.5 rushing, 153.0 passing  
2024: 97.6 rushing, 370.0 passing  
Shift: –115.9 rush, +217.0 pass; passing ~80% of 2024 offense.

**Verification**  
✅ Matches the typed values. Clear flip from run-heavy to pass-heavy.

---

### Q2 — Overall production
**Model Output**  
Yards/g: 366.5 → 467.6 (+101.1)  
Points/g: 24.9 → 34.1 (+9.2)  
Yards/play: 5.7 → 6.1  
Plays/g: 64.8 → 76.9 (+12.1)

**Verification**  
✅ Correct. More plays, more yards, more points.

---

### Q3 — Situational execution
**Model Output**  
3rd down: 32.9% → 49.0%  
TOP: 29:14 → 33:04 (+3:50)

**Verification**  
✅ Correct. Drives were longer and more effective.

---

### Q4 — Red-zone finishing
**Model Output**  
RZ scoring: 76.5% → 85.5%  
RZ TDs: 58.8% → 69.4%

**Verification**  
✅ Correct. More trips and better touchdown conversion.

---

### Q5 — Turnovers and sacks
**Model Output**  
TO margin: –5 → +1  
Sacks: 37 for / 32 against → 27 for / 29 against

**Verification**  
✅ Correct. Cleaner ball security; fewer defensive sacks.

---

### Q6 — Rushing efficiency
**Model Output**  
Offense: 5.2 → 3.2 (down 2.0)  
Defense: 3.5 → 5.0 (up 1.5)

**Verification**  
✅ Correct. Rushing and rush defense both weakened.

---

### Q7 — Discipline and kicking
**Model Output**  
Penalties: ~58–59 yds/g both years  
FG%: 64.3% → 59.1% (SU), 86.4% → 72.7% (Opp)

**Verification**  
✅ Correct. Penalties flat; FG% dipped slightly.

---

### Q8 — Fan demand
**Model Output**  
Average attendance: 32,461 → 39,130 (+6,669)  
Total: 227,224 → 273,913

**Verification**  
✅ Verified. Higher scoring and more wins correlated with higher turnout.

---

## 📈 Summary

- **Identity**: Run-first (2021) → Pass-first (2024)  
- **Production**: +100 yds/g, +9 pts/g, +12 plays/g  
- **Execution**: major gains in 3rd-down and red-zone efficiency  
- **Weaknesses**: rushing offense & rush defense regressed  
- **Discipline**: penalties stable  
- **Impact**: attendance up ~20%

---

## 🔍 Why Both Q&A and Notebook?

- **ChatGPT (GPT-4 & GPT-5)** → fast, readable narrative from first-page stats  
- **Notebook** → deterministic checks, **descriptive stats (W-L & Win% splits)**, and simple charts  
- **Together** → readable **and** verifiable

---

## ▶️ Running the Notebook

1. Open `Task_05_Syracuse_Football.ipynb`.  
2. Run all cells.  
3. The notebook:
   - Uses only the two dictionaries at the top as input (`season_2021`, `season_2024`).  
   - Prints **True/False** for each LLM claim.  
   - Shows **descriptive stats** for W-L and Win% splits.  
   - Plots yards/game, points/game, and plays/game.

---

## 🙋 Acknowledgments

This project was completed for **Syracuse University iSchool OPT Research Task 05**.  
The analysis and checks were written by me. **ChatGPT (GPT-4 and GPT-5)** assisted with drafting and structuring the Python notebook; I reviewed and finalized all code and numbers.
