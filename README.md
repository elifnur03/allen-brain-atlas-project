# Gene Expression in the Hippocampus vs Amygdala
### A bioinformatic analysis using the Allen Human Brain Atlas


**Data source:** [Allen Human Brain Atlas](https://human.brain-map.org) — open access  
**Tools:** Python · pandas · seaborn · matplotlib · numpy  

---

## What this project is about

The hippocampus and amygdala sit next to each other in the brain's medial temporal lobe, but they do completely different things. The hippocampus consolidates memories. The amygdala processes fear and emotion. This project asks: can we see that functional difference at the molecular level — in which genes each region expresses?

Using open-access gene expression data from the Allen Human Brain Atlas, I analyzed eight genes across four hippocampal subfields and four amygdalar nuclei, and found that the answer is yes, clearly and quantitatively.

---

## Research question

> Do the hippocampus and amygdala differ systematically in their gene expression profiles, and do those differences reflect their distinct functional roles in memory and emotion?

**Hypothesis:** Memory-related genes (BDNF, CAMK2A, GRIN2B) will be enriched in the hippocampus. Stress and emotion genes (CRH, NPY, SLC6A4) will be enriched in the amygdala. Structural genes (GAD1, APOE) will be similarly expressed in both.

---

## Genes analyzed

| Gene | Category | Role |
|---|---|---|
| BDNF | Memory & plasticity | Synaptic plasticity, neurogenesis |
| CAMK2A | Memory & plasticity | LTP induction, spatial memory |
| GRIN2B | Memory & plasticity | NMDA receptor; memory encoding |
| CRH | Stress & emotion | HPA axis, fear output |
| NPY | Stress & emotion | Anxiety regulation, fear extinction |
| SLC6A4 | Stress & emotion | Serotonin transporter; anxiety/PTSD risk |
| GAD1 | Structural | GABA synthesis; inhibitory neurons |
| APOE | Structural | Lipid transport; Alzheimer's risk gene |

---

## Brain regions analyzed

**Hippocampus:** CA1 · CA3 · Dentate gyrus · Subiculum  
**Amygdala:** Basolateral · Central nucleus · Lateral nucleus · Medial nucleus

---

## Key findings

- BDNF, CAMK2A, and GRIN2B are **3–4× more expressed** in hippocampal subfields than in amygdalar nuclei (log₂FC: +1.45 to +1.83)
- CRH is **~7.5× more expressed** in the amygdala than hippocampus (log₂FC: −2.93) — highest in the central nucleus, the amygdala's fear output station
- SLC6A4 and NPY show **2–4× amygdalar enrichment** (log₂FC: −1.74 to −1.96)
- GAD1 and APOE show **near-identical expression** in both regions (log₂FC: −0.10 and +0.03)
- The two regions' expression profiles are almost **mirror images** of each other when visualized on a radar chart

---


## How to run this project

### Option 1: Google Colab (recommended — no installation needed)
1. Go to [colab.research.google.com](https://colab.research.google.com)
2. File → Upload notebook → select `allen_brain_atlas_project.ipynb`
3. Run all cells top to bottom (Shift+Enter)

### Option 2: Local Python
```bash
git clone https://github.com/YOUR_USERNAME/allen-brain-atlas-project
cd allen-brain-atlas-project
pip install pandas numpy matplotlib seaborn allensdk
jupyter notebook allen_brain_atlas_project.ipynb
```

---

## Project structure

```
allen-brain-atlas-project/
│
├── allen_brain_atlas_project.ipynb   # Full analysis notebook (8 cells)
├── allen_brain_atlas_report.md       # Written scientific report (~1,700 words)
├── README.md                         # This file
│
├── figures/
│   ├── heatmap.png                   # Figure 1
│   ├── bar_comparison.png            # Figure 2
│   ├── fold_change.png               # Figure 3
│   └── radar.png                     # Figure 4
```

---

## What I learned

This project taught me that the functional specialization we observe behaviorally and in neuroimaging is directly encoded at the molecular level. The proteins a brain region manufactures are not incidental — they are the mechanism. BDNF is concentrated in the dentate gyrus because the dentate gyrus is actively growing new neurons. CRH is concentrated in the central nucleus because the central nucleus is the amygdala's fear output station. Gene expression data is not just a readout of biology — it is an explanation of it.

The analysis also made me appreciate the importance of anatomical specificity. Treating "the hippocampus" or "the amygdala" as single units would have obscured real within-structure variation. The dentate gyrus behaves differently from CA1; the central nucleus behaves differently from the basolateral complex. Resolution matters.

---

## References

Hawrylycz, M. J., et al. (2012). An anatomically comprehensive atlas of the adult human brain transcriptome. *Nature*, 489, 391–399.

LeDoux, J. E. (2000). Emotion circuits in the brain. *Annual Review of Neuroscience*, 23, 155–184.

Squire, L. R. (2004). Memory systems of the brain: A brief history and current perspective. *Neurobiology of Learning and Memory*, 82(3), 171–177.

---

*This project was completed independently as part of a self-directed neuroscience portfolio. All data are open-access via the Allen Brain Atlas. Feedback welcome.*
