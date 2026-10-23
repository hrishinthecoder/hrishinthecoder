<p align="center">
  <img src="assets/banner.svg" width="100%" alt="Hrishin Debnath: research enthusiast and data analyst in Dhaka, Bangladesh">
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/hrishin-debnath/"><img src="https://img.shields.io/badge/LinkedIn-hrishin--debnath-9a3412?style=for-the-badge&labelColor=1c1917" alt="LinkedIn"></a>
  <a href="https://hrishinthecoder.github.io"><img src="https://img.shields.io/badge/Portfolio-hrishinthecoder.github.io-1c1917?style=for-the-badge&labelColor=9a3412" alt="Portfolio"></a>
  <a href="mailto:i.am.hrishin@gmail.com"><img src="https://img.shields.io/badge/Email-i.am.hrishin%40gmail.com-9a3412?style=for-the-badge&logo=gmail&logoColor=f6f1e7&labelColor=1c1917" alt="Email"></a>
  <img src="https://img.shields.io/badge/Open%20to-internships%20%26%20research%20mentorship-78716c?style=for-the-badge&labelColor=1c1917" alt="Open to internships and research mentorship">
</p>

Hi, I'm Hrishin. I'm a higher-secondary science student in Dhaka who turns public data into research. I have written two air-quality papers on my own, both now under review, and I'm testing whether language models answer medical questions worse in Bangla than in English. I also build tools I need myself, like a study app that catches me reaching for my phone.

<p align="center">
  <img src="assets/highlights.svg" width="100%" alt="Research highlights: 36% PM2.5 drop during Eid; forecast 5.22 µg/m³ better than persistence; 12,000 medical exam questions translated to Bangla">
</p>

## 🔬 Research

<table>
<tr>
<td width="50%" valign="top">

**Does Dhaka's air get cleaner when the city empties?**<br>
<sub>Sole author · under review at the <i>Columbia Junior Science Journal</i></sub>

Eid empties Dhaka every year, which makes it a natural experiment. Across 16 Eid holidays (2016–2024) and 75,325 hourly readings from the US Embassy monitor, PM2.5 fell by **36%**.

<a href="https://github.com/hrishinthecoder/dhaka-eid-pm25"><img src="https://raw.githubusercontent.com/hrishinthecoder/dhaka-eid-pm25/main/figures/Figure1.png" alt="PM2.5 around Eid holidays in Dhaka"></a>

[Code and data →](https://github.com/hrishinthecoder/dhaka-eid-pm25)

</td>
<td width="50%" valign="top">

**Next-day PM2.5 forecasting in Dhaka**<br>
<sub>Sole author · under review at <i>Air Quality, Atmosphere &amp; Health</i></sub>

I built two independent pipelines from a single reference-grade monitor, ERA5 weather and satellite fire data. XGBoost beat the "tomorrow = today" baseline by **5.22 µg/m³** RMSE (p = 0.022), and a separate LightGBM build reached the same result.

<a href="https://github.com/hrishinthecoder/dhaka-pm25-forecast"><img src="https://raw.githubusercontent.com/hrishinthecoder/dhaka-pm25-forecast/main/approach2/reports/figures/pred_vs_actual_xgboost.png" width="78%" alt="Predicted vs actual next-day PM2.5"></a>

[Code, frozen model and checksums →](https://github.com/hrishinthecoder/dhaka-pm25-forecast)

</td>
</tr>
</table>

## 🛠️ Desk Watch

<sub>Open source · v0.1.0-beta · Windows · MIT</sub>

I kept picking up my phone while studying, so I built an app that notices. Desk Watch uses the webcam, entirely on the computer, and rings an alarm when you pick up a phone, leave the desk, look away or fall asleep. It also blocks distracting sites and apps, runs Pomodoro sessions, plans your tasks, and works in English and Bangla. Nothing is recorded or uploaded.

I built it with Claude Code: I wrote about 60% of the code, set the requirements, made the design decisions, recorded the training clips and tested each stage.

**How it works.** Every frame stays on the computer. Detectors turn each frame into a few signals; time rules turn signals into alarms, so a quick glance or a blink never rings.

```mermaid
flowchart LR
    CAM["Webcam frame"] --> FACE["MediaPipe face landmarks<br/>eyes open or closed, head direction"]
    CAM --> HAND["MediaPipe hands + person box"]
    CAM --> OBJ["Phone detector<br/>(custom model, trained on my clips)"]
    FACE --> RULES{"Time rules"}
    HAND --> RULES
    OBJ --> RULES
    WIN["Front window + browser extension"] --> BLOCK{"Blocker mode<br/>10 s warning first"}
    RULES -->|"phone in hand or at ear"| ALARM["Alarm<br/>study clock stops"]
    RULES -->|"nobody at the desk"| ALARM
    RULES -->|"looking away too long"| ALARM
    RULES -->|"eyes closed 6 s or head down 15 s"| ALARM
    BLOCK -->|"blocked app or site stays open"| ALARM
    RULES -->|"all clear"| CLOCK["Study clock runs"]
    ALARM --> LOG[("Local database<br/>sessions, history, stats")]
    CLOCK --> LOG
```

[Code →](https://github.com/hrishinthecoder/desk-watch) · [Download the beta →](https://github.com/hrishinthecoder/desk-watch/releases)

## 🌱 What I'm doing now

- **Research intern, CreateBud Inc.** I'm building a Bangla version of the MedQA medical exam set (12,000 questions) to measure whether LLMs answer worse in Bangla than in English.
- **Market analyst, VibeWeave.** Market studies of India's textile industry and a verified database of 26 clothing manufacturers.
- **NASA Space Apps Challenge 2026, Team Obsidian Prime.** Technical lead on *Baseline*, a prototype that compares an astronaut's daily health readings with their own normal range and cites the NASA study behind every flag. [Repo →](https://github.com/obsidianprimeofficial-alt/baseline)
- **Deputy Director of R&D, CORViS.** I run the *Speaks Academia* seminar series.
- **Next:** language disparity in LLMs, and whether image-generation models do worse with Bangla prompts.

## 📂 Selected projects

| Project | What it shows | Tools |
|---|---|---|
| [**dhaka-eid-pm25**](https://github.com/hrishinthecoder/dhaka-eid-pm25) | Event study, bootstrap CIs, placebo tests and weather control on 9 years of hourly data | Python, pandas, SciPy |
| [**dhaka-pm25-forecast**](https://github.com/hrishinthecoder/dhaka-pm25-forecast) | Leak-free forecasting, Diebold–Mariano test, rolling backtest, SHAP, frozen artifacts | Python, XGBoost, LightGBM |
| [**desk-watch**](https://github.com/hrishinthecoder/desk-watch) | On-device webcam app that alarms on phone use, leaving the desk or dozing off; blocker, planner, Bangla UI | TypeScript, Electron, MediaPipe |
| [**Saas_Cohort_Model**](https://github.com/hrishinthecoder/Saas_Cohort_Model) | Customer retention falls to ~70% by month 12 while revenue retention holds near 95%; Monte Carlo NRR range 83–110% | Excel, Power Query, DAX |
| [**elevvo-pathways-internship**](https://github.com/hrishinthecoder/elevvo-pathways-internship) | RFM segmentation of 1,998 customers: 306 "Champions" made 23.81% of revenue | Python |
| [**bellabeat_case_study**](https://github.com/hrishinthecoder/bellabeat_case_study) | Google Data Analytics capstone: smart-device habits turned into marketing advice | R, SQL |

## 🧰 Toolbox

<p>
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/SQL-336791?style=flat-square&logo=postgresql&logoColor=white" alt="SQL">
  <img src="https://img.shields.io/badge/R-276DC3?style=flat-square&logo=r&logoColor=white" alt="R">
  <img src="https://img.shields.io/badge/pandas-150458?style=flat-square&logo=pandas&logoColor=white" alt="pandas">
  <img src="https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white" alt="scikit-learn">
  <img src="https://img.shields.io/badge/XGBoost-1F6FEB?style=flat-square" alt="XGBoost">
  <img src="https://img.shields.io/badge/LightGBM-2E7D32?style=flat-square" alt="LightGBM">
  <img src="https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white" alt="Jupyter">
  <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript">
  <img src="https://img.shields.io/badge/Electron-47848F?style=flat-square&logo=electron&logoColor=white" alt="Electron">
  <img src="https://img.shields.io/badge/Power%20BI-F2C811?style=flat-square&logoColor=black" alt="Power BI">
  <img src="https://img.shields.io/badge/Tableau-E97627?style=flat-square" alt="Tableau">
  <img src="https://img.shields.io/badge/Excel%20%C2%B7%20Power%20Query%20%C2%B7%20DAX-217346?style=flat-square" alt="Excel, Power Query, DAX">
  <img src="https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white" alt="Git">
</p>

**Certificates:** WorldQuant University Applied Data Science Lab · Google Data Analytics · Google Business Intelligence · HackerRank SQL (Advanced) · freeCodeCamp Data Analysis with Python

<p align="center"><sub>Dhaka, Bangladesh · UTC+6</sub></p>
