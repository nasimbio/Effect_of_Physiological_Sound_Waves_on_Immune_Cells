# Multiplexed scRNA-seq Analysis: Effect of physiological Sound Waves on Immune Cells Transcriptomic Profile


## 📘 Project Overview
 
There are **30 libraries total**, Each library contains **8 samples**,  representing **240 samples** from **12 human subjects** across 5 randomized study visits.
The **4 samples from each study visit** are always grouped and processed together. 

This project investigates the transcriptomic effects of physiological sound wave stimulation on human immune cells, both with and without lipopolysaccharide (LPS) in different treatments to explore how immune cell states respond to both physical and chemical stimulation.

---

## 📊 Analysis Tasks

### **Task 1: Preprocessing, Demultiplexing, and QC**
- Created Seurat objects for each sample from gene expression matrices
- Integrated Hashtag Oligonucleotide (HTO) data as a separate assay
- Performed HTO demultiplexing using `MULTIseqDemux` with a 0.99 quantile threshold
- Merged all demultiplexed samples into a single Seurat object
- Added metadata for subject ID, treatment group, and study visit
- Visualized QC metrics using violin plots (`nCount_RNA`, `nFeature_RNA`, `nCount_HTO`, `percent.mt`)
- Removed low-quality cells, doublets, and negative droplets
- Normalized, scaled, and clustered the filtered dataset using Seurat's standard pipeline

### **Task 2: Differential Expression and GO Enrichment Analysis**
- Built a custom function to automate **DGE analysis** using `FindMarkers` (Wilcoxon test)
- Subset cells based on LPS and treatment groups and compared conditions
- Applied thresholds: logFC > 0.5 and p-value < 0.05
- Visualized DEGs using **volcano plots** (`EnhancedVolcano`)
- Performed **Gene Ontology (GO) enrichment** using `clusterProfiler`
- Converted gene symbols to Entrez IDs using `org.Hs.eg.db`
- Generated GO term dot plots for both upregulated and downregulated gene sets

### **Task 3: Cell-Cell Communication Analysis with CellChat**
- Processed the Seurat object for **CellChat** input
- Performed ligand-receptor network inference across treatment groups
- Compared communication patterns between different conditions

---

## 💡 Notes

- Raw data is not publicly available due to client ownership and confidentiality.
- Some example outputs plots are organized by task in the `output/` folder.
- This project is designed for both reproducibility and clarity.

---

## 📬 Contact

*Author:* Nasim Rahmatpour 
*Email:* nasimrahmatpour1@gmail.com 
*GitHub:* (https://github.com/nasimbio)
