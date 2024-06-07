Here's a detailed README file based on the content extracted from your PDF:

---

# Operationalizing a “Functional Potential Score” (FPS) to Prioritize GWAS Variants for Experimental Studies

## Introduction
This project focuses on operationalizing a Functional Potential Score (FPS) to prioritize genetic variants identified through Genome-Wide Association Studies (GWAS) for further experimental validation. The aim is to streamline the identification of functional/regulatory SNPs (Single Nucleotide Polymorphisms) that contribute to disease susceptibility, thereby enhancing the efficiency of downstream clinical translation.

## Author
- **Dhruv Jain**: [dj9304a@american.edu](mailto:dj9304a@american.edu)
- **Mentor**: Dr. Matthew F. Buas

## Project Overview
### 1. The Challenge
GWAS have successfully identified statistical associations between genetic variants and disease risk. However, pinpointing the functional/causal variants and understanding their underlying mechanisms remains a significant challenge. Many GWAS index variants are located in non-coding regions and are in linkage disequilibrium with numerous other SNPs, complicating the identification process. Experimental validation, although essential, is resource-intensive.

### 2. Approach
#### 2.1 Functional Potential Score (FPS)
FPS is a composite SNP-level metric designed to summarize the overall evidence for a variant's functional or regulatory potential. The score is calculated by integrating multiple annotation data inputs, each weighted based on their relevance and contribution to SNP functionality.

#### 2.2 Assigning SNP Calls Based on Annotation Overlap
SNP calls are assigned based on the overlap with various functional annotations. Key annotations include:
- dbSNP
- Zoonomia (conservation data)
- ENCODE (TF motifs, ATAC-seq, DNase I hypersensitivity)
- Cancer Genome Atlas (TCGA)
- ReMap2022 (TF ChIP-seq)
- Roadmap/ENCODE (HMM-15, enhancer, super-enhancer)
- GTEx (eQTL)
- JEME and 4DGenome (3D linkages)

#### 2.3 LASSO Regression
LASSO (Least Absolute Shrinkage and Selection Operator) regression is employed to identify the most predictive features for SNP functionality. The model incorporates a penalty term (λ) to control the amount of shrinkage applied to model coefficients, promoting sparsity and reducing overfitting. The optimal λ value is determined through 5-fold cross-validation.

#### 2.4 Training and Testing Data
The dataset used includes Massively Parallel Reporter Assay (MPRA) data on 1,992 variants from 54 melanoma GWAS loci. These SNPs exhibit allelic-specific transcriptional activity, and the data is split into training (2/3) and testing (1/3) sets for model building.

## Results
### 3.1 Assembly of FPS Feature Call Variables
### 3.2 Model Building using LASSO
The LASSO model identified key annotation inputs that are most predictive of SNP regulatory function:
- DHS (c5_1, c5n_K)
- TF-ChIP-seq (c6n_K, c6_3)
- Sequence conservation (c2n)

### 3.3 Assessment of Model Performance
The FPS model effectively integrates tissue-specific annotations to prioritize functional variants, demonstrating its potential to enhance experimental study efficiency.

## Conclusions
- The integration of tissue-specific annotations into the FPS can significantly improve the prioritization of GWAS variants for experimental validation.
- The LASSO regression model successfully identified key predictors of SNP functionality, highlighting the importance of specific annotation inputs.

## References
- Chen, J., ..., Buas, M. F. (2022). Prioritization and functional analysis of GWAS risk loci for Barrett’s esophagus and esophageal adenocarcinoma. Hum Mol Genet. 31: 410–422.
- Ali MW, …, Buas M.F. (2022) A risk variant for Barrett's esophagus and esophageal adenocarcinoma at chr8p23.1 affects enhancer activity and implicates multiple gene targets. Hum Mol Genet. 31:3975-3986.
- Long, E., et al. (2022) Massively parallel reporter assays and variant scoring identified functional variants and target genes for melanoma loci and highlighted cell-type specificity. Am J Hum Genet. 109:2210–2229.
- Cano-Gamez, E., & Trynka, G. (2020) From GWAS to Function: Using Functional Genomics to Identify the Mechanisms Underlying Complex Diseases. Front Genet. 11:424.

## Acknowledgements
I gratefully acknowledge support from the National Cancer Institute (R25CA272282), the National Institute of Diabetes and Digestive and Kidney Diseases (R01DK128615), the MSK Society, and my dedicated mentor, Dr. Buas.

## Contact
For further information or inquiries, please contact Dhruv Jain at [dj9304a@american.edu](mailto:dj9304a@american.edu).

---

Feel free to review and adjust this README file according to your needs. If you need any modifications or additional details, please let me know!
