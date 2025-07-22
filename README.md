# Multiplexed scRNA-seq Analysis: Effect of physiological Sound Waves on Immune Cells Transcriptomic Profile


## 📘 Project Overview
 
There are **30 libraries total**, Each library contains **8 samples**,  representing **240 samples** from **12 human subjects** across 5 randomized study visits.
Each sample before treatment and after treatment was exposed to the the physiological sound (LPS)
This project investigates the transcriptomic effects of physiological sound wave stimulation on human immune cells, in different treatments to explore how immune cell states respond to both physical and chemical stimulation.

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
- Normalized, scaled, and clustered the filtered dataset

### **Task 2: Differential Expression and GO Enrichment Analysis**
- Built a custom function to automate **DGE and GO Enrichment analysis** to perform the following comparisons:

1) Intra Signal Analysis (for each treatment separately)
- Post vs Pre Treatment without LPS (5 comparisons: for 1 control and 4 treatments)
- Post vs Pre Treatment with LPS (5 comparisons: for 1 control and 4 treatments)
- Pre Treatment with LPS vs Pre Treatment without LPS (5 comparisons: for 1 control and 4 treatments)
- Post Treatment with LPS vs Post Treatment  without LPS (5 comparisons: for 1 control and 4 treatments)

2) Inter Signal Analysis (each treatment compared to the control) 
- Pre treatment without LPS vs control pre without LPS (4 comparisons, each treatment vs. control)
- Post treatment without LPS vs control post without LPS (4 comparisons, each treatment vs. control)
- Pre treatment with LPS vs control pre with LPS (4 comparisons, each treatment vs. control)
- Post treatment with LPS vs control post with LPS (4 comparisons, each treatment vs. control)



### **Task 3: Cell-Cell Communication Analysis with CellChat for the same Inter and Intra comparisons**
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
