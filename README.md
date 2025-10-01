# CattleSeqGWAS
This project conducts a sequence-based GWAS in Belgian Blue cattle by combining HD genotypes with WGS from 230 bulls to impute sequence-level variants in ~15K animals. The imputed data were analyzed across 11 traits, and significant markers defined QTL regions and credible sets, enabling the detection of candidate genes for growth and body size.

The pipeline covers:  
- Quality control of sequence data (SNPs & INDELs)  
- Phasing & imputation from HD to sequence level  
- Single-trait and multi-trait GWAS using LMM (GEMMA)  
- Fine-mapping with credible sets (LD-based & Bayesian IBSS)  
- Conditional mapping to detect additional signals in QTL regions  

### 1. Imputation HD → Sequence Level  
Folder: `SEQUENCE_PANEL`  
- Quality control of raw sequence genotypes (230 bulls)  
- SNP and INDEL filtering by VQSR (97.5 threshold)  
- Phasing with SHAPEIT4.2  
- Imputation with Minimac4 (~15K animals)  

### 2. Sequence Animals + Phenotypes  
Folder: `SEQUENCE_ANIMALS_PHENOTYPES`  
- Extraction of imputed genotypes + phenotypes (~14,762 cows)  
- Conversion to PLINK BED format  
- Preparation for GWAS analyses  

### 3. Single-Trait GWAS  
Folder: `SINGLE_TRAIT`  
- Linear Mixed Model (GEMMA) per trait  
- Manhattan plots, LocusZoom, correlation plots  
- Fine-mapping: LD-based CS (r² >0.8, >0.9) & Bayesian SuSiE  

### 4. Multi-Trait GWAS  
Folder: `MULTIPLE_TRAIT`  
- Joint analysis of longitudinal traits and muscular traits  
- LMM with GEMMA  
- Fine-mapping & credible sets  

### 5. Comparison of Fine-Mapping (ST vs. MT)  
Folder: `COMPARISON_CS_ST_MT`  
- Integration of credible sets across models  
- Annotation of candidate variants  

### 6. Conditional Mapping  
Folders: `CONDITIONAL_MAPPING_ST` and `CONDITIONAL_MAPPING_MT`  
- Conditioning on 11 lead SNPs (significant regions of 10 Mb)  
- Detection of additional QTL signals  
- Iterative mapping (two-step strategy)  
