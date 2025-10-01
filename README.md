# CattleSeqGWAS
This project conducts a sequence-based GWAS in Belgian Blue cattle by combining HD genotypes with WGS from 230 bulls to impute sequence-level variants in ~15K animals. The imputed data were analyzed across 11 traits, and significant markers defined QTL regions and credible sets, enabling the detection of candidate genes for growth and body size.

The pipeline covers:  
- Quality control of sequence data (SNPs & INDELs)  
- Phasing & imputation from HD to sequence level  
- Single-trait and multi-trait GWAS using LMM (GEMMA)  
- Fine-mapping with credible sets (LD-based & Bayesian IBSS)  
- Conditional mapping to detect additional signals in QTL regions  
