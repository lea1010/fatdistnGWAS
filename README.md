# Meta-analysis of fat distribution phenotypes in UK Biobank and GIANT
Included in this repository is code and data related to the manuscript 'Meta-analysis of genome-wide association studies for body fat distribution in 694,649 individuals of European ancestry' (available on bioRxiv here: XXX)


#### 1. run.bolt.ukbb-anthropometric.sh 
Script for running a genome-wide association study on UK Biobank data, using BOLT-LMM  <br />
Usage: ```./run.bolt.ukbb-anthropometric.sh phenotype ldsc_panel grm grm_snp_subset sex```

#### 2. run.bolt-reml.ukbb-anthropometric.sh
Script for estimating heritability of a trait using UK Biobank data and the restricted maximum likelihood (REML) method implented in BOLT-LMM (i.e., BOLT-REML)  <br />
Usaage: ```./run.bolt-reml.ukbb-anthropometric.sh phenotype ldsc_panel grm grm_snp_subset sex```

#### 3. build_grm.sh
Script for generating data to use as the genetic relationship matrix (GRM) when running BOLT-LMM. The script contains steps to generate a GRM from either genotyped or imputed data  <br />
Usage: ```./build_grm.sh chr imputed_or_genotyped```

#### 4. anthropometricPheno.fat-distn.R
R script for generating phenotypes from UK Biobank data. Specifically, this script helps standardize and normalize the body mass index and waiste-hip ratio traits, as well as generate the waist-hip ratio adjusted for BMI trait. <br />
Usage: ```Rscript anthropometricPheno.fat-distn.R```

#### 5. gctaSelect.sh
Script that calls the GCTA software (http://cnsgenomics.com/software/gcta/GCTA_UserManual_v1.24.pdf) to run joint conditional analysis (to determine independent signals within a single genomic loci). This script can be used to determine independetly-associated signals in the UK Biobank-only GWAS (i.e., the 'meta' argument set to 0) or from the meta-analysis ('meta' argument set to 1). <br />
Usage: ```./gctaSelect.sh phenotype sex chromosome significance_level meta```

#### 6. ldscores.sh
Script for generating LD Scores (https://github.com/bulik/ldsc) from PLINK-formatted data. The GRM can included imputed or genotyped data, contain pruned or unpruned SNPs. <br />
Usage: ```./ldscores.sh grm pruned sample_set chr```

#### 7. ldsc-intercept.sh
Script for estimating the LD Score intercept from GWAS summary-level data. <br />
Usage: ```./ldsc-intercept.sh phenotype sex ldsc_panel```

#### 8. run_metal.sh
Example script for running meta-analysis in METAL (https://genome.sph.umich.edu/wiki/METAL_Documentation). <br />
Usage: ```./run_metal.sh metal_params.example.txt``` <br />
The file metal_params.example.txt is provided as part of this repository.

