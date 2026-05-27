# Human Motor Cortex Gene Expression
**Author:** Alex Nite   
**Dataset:** Human M1 single‑nucleus transcriptomes (76,533 nuclei)

---

##  Project Overview
This project analyzes high‑resolution single‑nucleus transcriptomic data from the human primary motor cortex (M1) to understand how gene expression varies across neuronal subclasses, cortical layers, donor sex, and major cell classes. The dataset includes **76,533 nuclei** and **trimmed mean expression values** across dozens of neuronal and non‑neuronal clusters.

The goal was to test four hypotheses related to neuronal identity, neurotransmission, and cell‑type‑specific gene expression patterns.

---

##  Research Questions / Hypotheses
1. **SST vs VIP neurons** show significantly different gene expression profiles.  
2. **Donor sex** produces small but detectable differences in gene expression within some neuron types.  
3. **Neurotransmission‑related genes** vary across cortical layers.  
4. **Marker genes** are strongly associated with GABAergic, Glutamatergic, or Non‑neuronal cell classes.

These hypotheses are grounded in prior literature on cortical organization, laminar specialization, and transcriptomic diversity.

---

## Background & Motivation
The M1 cortex is essential for voluntary movement and is implicated in disorders such as ALS and Parkinson’s disease. Understanding its molecular architecture helps clarify:

- How neuronal subpopulations differ  
- How cortical layers specialize  
- How gene expression relates to function  
- How sex‑linked differences may appear in the brain  

Prior studies (Watakabe 2007; Miller 2019; Vawter 2004; Jacques 2011) show that cortical neurons can be distinguished by gene expression, laminar position, and developmental lineage. This project extends those ideas using modern single‑nucleus RNA‑seq data.

---

##  Methods

### **1. Data Import & Inspection**
- Loaded **trimmed_means.csv** and **metadata.csv** into R  
- Used `glimpse()` and `summary()` to examine structure  
- Identified relevant columns for each hypothesis  

### **2. Subsetting for Each Hypothesis**
- **H1:** Extracted SST and VIP subclasses  
- **H2:** Compared male vs female donor nuclei  
- **H3:** Selected neurotransmission‑related genes across cortical layers  
- **H4:** Grouped by GABAergic, Glutamatergic, and Non‑neuronal classes  

### **3. Data Cleaning**
- Calculated proportion of zeros per gene  
- Removed genes with **>95% zero values**  
- Ensured only meaningful expression values remained  

### **4. Statistical Tests**
- **Two‑sample t‑tests** for two‑group comparisons (H1, H2)  
- **ANOVA** for multi‑group comparisons (H3, H4)  
- Retained only significant results (**p < 0.05**)  

### **5. Visualization**
- Bar plots for SST vs VIP and male vs female  
- Boxplots for layer‑specific expression  
- Boxplots + density plots for cell‑class comparisons  

---

##  Key Findings

### **H1 – SST vs VIP Neurons**
- Multiple genes showed significant differential expression  
- Confirms that SST and VIP subclasses have distinct molecular identities  

### **H2 – Donor Sex Differences**
- Only small, subtle differences detected  
- Supports literature showing sex‑linked expression exists but is limited in cortex  

### **H3 – Neurotransmission Genes Across Layers**
- Several neurotransmission‑related genes varied significantly by cortical layer  
- Suggests laminar specialization in synaptic signaling  

### **H4 – Cell‑Class Marker Genes**
- Strong associations found between marker genes and:  
  - **GABAergic** neurons  
  - **Glutamatergic** neurons  
  - **Non‑neuronal** cells  
- Confirms expected molecular signatures of major cortical classes  

---

##  Interpretation
The results align with prior research showing:

- Clear molecular distinctions between inhibitory neuron subclasses  
- Subtle sex‑linked gene expression differences  
- Strong laminar organization of neurotransmission genes  
- Robust marker‑gene signatures for major cell classes  

This supports the idea that the M1 cortex contains highly specialized neuronal populations with distinct molecular roles.

---

##  Challenges
- High sparsity in single‑nucleus data required filtering  
- Some genes had extreme outliers  
- Wide‑to‑long transformations were necessary for plotting  
- Large dataset required careful subsetting and memory management  

---

##  Future Directions
- Expand analysis to full gene set (20,000+ genes)  
- Apply clustering to identify novel neuronal subtypes  
- Use dimensionality reduction (PCA/UMAP) for visualization  
- Explore differential expression across disease states (e.g., ALS)  
- Integrate spatial transcriptomics for laminar mapping  

---
