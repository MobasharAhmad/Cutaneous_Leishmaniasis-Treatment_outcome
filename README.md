# Cutaneous_Leishmaniasis-Treatment_outcome
Among the three types, cutaneous leishmaniasis is the most common form; it causes skin ulcers that may eventually be metastatic and is caused by protozoan parasites, with sandflies acting as the vector. Patients treated with antiparasitic drugs show variable outcomes; some of them are not cured. Alterations in gene expression between patients' lesions may stimulate certain pathways, which can be linked to treatment failure. Why this alteration happens between patients could be another interesting question. In this paper [Variable gene expression and parasite load predict treatment outcome in cutaneous leishmaniasis](https://www.science.org/doi/10.1126/scitranslmed.aax4204), authors collected biopsies of lesions from patients before treatment and skins from healthy individuals, performed bulk RNAseq analysis and concluded that the treatment failure of pentavalent antimony was associated with cytotoxic pathway stimulated during the infection. They also showed that parasitic load could predict treatment outcome in advance. The datasets are publicly available through the Gene Expression Omnibus (GEO) under accession number [GSE127831](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE127831).


> I aimed to **reanalyze** the samples (7 healthy and 21 diseased) completely from raw fastq to develop own curated Bulk RNAseq Analysis workflow, reproduce the plots (are the same findings observed?) and explore new biological insights by incorporating complementary analyses.


## Workflow
```
                                              *Activity (Tools used)*
Programmatically downloaded the datasets (Kingfisher v0.4.1)
   ↓
Prepared the Study design file (bash) & Renamed the fastq files programmatically (bash)
   ↓
Checked the quality of raw fastq files (FastQC v.0.12.1 and MultiQC V1.33)
   ↓
Trimmed low quality bases, adapters, bad reads (fastp 1.0.1)
   ↓
Checked the quality of trimmed fastq files (FastQC v.0.12.1 and MultiQC V1.33)
   ↓
Mapped the reads (kallisto 0.48.0)
   ↓
[Following works (inside the box) were done in Rstudio (R version 4.5.2)]
---------------------------------------------------------------------------------------------------
Annotated the transcripts and imported the abundance file
   ↓
Filtered and normalized the counts
   ↓
Principal Component Analysis
   ↓
Differential Gene Expression Analysis
   ↓
Module Identification [Supervised]
   ↓
Functional Enrichment Analysis
   ↓
Differential Transcript Usage Analyses
------------------------------------------------------------------------------------------------------
 ↓
Gene Co-expression Analysis [Unsupervised clustering]
```

## Analyses
### Principal Component Analysis: Reproducing Figure 1A
<img width="906" height="897" alt="PCA_1A" src="https://github.com/user-attachments/assets/ceda4aed-4f26-490f-8cbe-2d2c516c44e8" />


### Volcano plot for DEGs: Reproducing Figure 1B
<img width="1196" height="752" alt="Volcano_plot_1B" src="https://github.com/user-attachments/assets/32a4777b-8ee4-412a-bbeb-8dbc91f5fb35" />  





### Enrichment plot for GSEA: Reproducing Figure 1C
<img width="1548" height="1023" alt="Enrichment_plot002_1C" src="https://github.com/user-attachments/assets/2d545519-fbc3-4658-8bee-49a8c2ce30c0" />


















 
