# Kiran Shah
### Houston Dynamo Data Analyst Application Project - 2024 Striker Recruitment
Identify and recommend a striker for Houston Dynamo FC using integrated tracking and event data, focusing on athleticism, movement, and production.

Data: Skillcorner GI | Skillcorner Physical | Wyscout

---

## Approach

This project integrates tracking-derived physical and off-ball metrics from SkillCorner with on-ball production data from Wyscout to evaluate striker profiles holistically.

The analysis follows four core steps:

**1. Metric Definition**  
Athleticism and movement were captured using:
- High-speed running distance and sprint frequency  
- Peak sprint velocity (PSV-99)  
- Acceleration and change-of-direction counts  
- Off-ball run metrics (total runs, targeted runs, dangerous runs, penalty-area runs)

Production was defined using:
- Goals and expected goals (xG)  
- Shots and touches in the box  
- Dribbles and offensive duels  

**2. Data Preparation & Integration**  
- SkillCorner match-level data was aggregated to the player-season level  
- Wyscout data (already per-90) was merged using the player ID mapping file  
- Merge validation checks were performed to ensure consistency across datasets  

**3. Filtering Logic**  
- Position filter: attacking roles (forward/wing/attacking midfield profiles)  
- Minutes thresholds applied to ensure statistical reliability and meaningful physical samples  
- Players with incomplete tracking data were removed to maintain consistency  

**4. Ranking & Shortlisting**  
- Composite evaluation combining physical output, movement quality, and production  
- Players were shortlisted based on strong performance across both athletic and production dimensions  
- Final selection prioritizes players who demonstrate both dynamic movement and end-product  

---

## Results

A shortlist of high-performing attacking players was generated based on the defined criteria.

The final recommendation is a player who:
- Demonstrates elite off-ball movement and physical output  
- Sustains consistent attacking production (xG, shots, box involvement)  
- Balances athletic profile with tangible on-ball impact  

Supporting outputs include:
- Player comparison scatterplots (movement vs production)  
- Radar charts highlighting multi-dimensional profiles  
- A final player profile visualization summarizing strengths  

The recommendation reflects a balance between measurable performance and recruitment practicality, while acknowledging that tactical fit, salary, and scouting context are not captured in this dataset.

---

## Repository Structure

houston-dynamo-striker-recruitment/
├── README.md  
├── requirements.txt  
├── ai_prompts.md  
├── data/  
│   ├── raw/              # Place provided CSV files here  
│   └── processed/        # Aggregated and merged datasets  
├── notebooks/  
│   ├── 01_eda.ipynb  
│   └── 02_striker_recruitment_workflow.ipynb  
├── outputs/  
│   ├── figures/          # Visualizations used in analysis  
│   └── tables/           # Final datasets and summaries  
└── presentation/  
    └── Kiran_Shah_Houston_Dynamo_Striker_Recruitment.pdf  
    
---

## Requirements

- Python 3.10+
- pandas, numpy, matplotlib, mplsoccer

### How to Run

1. Clone the repository  
2. Place provided CSV files in `/data/raw`:
   - `skillcorner_gi_2024_mls.csv`
   - `skillcorner_physical_2024_mls.csv`
   - `wyscout_2024_mls.csv`
   - `player_id_map.csv`
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
4. Run notebooks in order:
    - notebooks/01_eda.ipynb
    - notebooks/02_striker_recruitment_workflow.ipynb
Note: Some Python 3.13 environments may produce compatibility issues with certain packages (e.g., mplsoccer). Python 3.10–3.12 is recommended.
