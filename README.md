 
# **Contrasting cryptofaunal responses to seabird nutrient inputs illuminate coral reef productivity pathways code and data**

**This repository contains code and data presented in the article**:
  
Authors (anonymized). Contrasting cryptofaunal responses to seabird nutrient inputs illuminate coral reef productivity pathways. 

 

## 1. How to download this project?

On the project main page on Anonymous GitHub, click on the button `Download Repository` and then extract the ZIP folder.



## 2. Description of the project

### 2.1 Project organization

This project is organized in 3 folders:
  
* :file_folder:	`data` folder contains 10 datasets and map files  (see **2.2 Datasets description**).
* :file_folder:	`code` folder contains one Rmd file (see **2.3 Code description**).
* :file_folder:	`figures` folder contains 2 empty subfolders (`main` and `supp`) for saving figures and one subfolder `silhouettes` containing 2 PNG files.


### 2.3 Datasets description

* Aenesthetic stations datasets

The following CHA23 datasets correspond to data collected in the Chagos archipelago, Indian Ocean, between the 17/10/2023 and the 31/10/2023, and results from associated analyses (stable isotope data).

The dataset _CHA23_Fish_data.csv_ corresponds to all fish data sampled using anaesthetic stations, and contains the following variables:
- `ID` Sample ID
- `Site` Sampling site
- `GENSPE` Genus and species
- `FAM` Family
- `TL` Total length (mm)
- `W` Weight (g)
- `TUBE_g` Sampling tube (ethanol)
- `TUBE_SIA` Sampling tube (oven-dried)

  The dataset _CHA23_Invert_data.csv_ corresponds to all invertebrate data sampled using anaesthetic stations, and contains the following variables:
- `Site` Sampling site
- `Taxa` Taxonomic level
- `Cara_L` Carapace width (mm)
- `TL` Total length (mm)
- `Arm_diam` Basal arm diameter (mm)
- `W` Weight (g)
- `TUBE_g` Sampling tube number (ethanol)
- `TUBE_SIA` Sampling tube number (oven-dried)

The dataset _CHA23_Site_info.csv_ corresponds to site-specific information, and contains the following variables:
- `Site` Site ID
- `Date` Sampling data
- `Atoll`
- `Island`
- `Location` Lagoon or outer reef
- `Treatment` Seabird-rich (Birdy) or rat-infested (Ratty)
- `CSL` Curved surface length
- `Condition` Excluded from community-level analyses if swell

The dataset _CHA23_SIA_data.csv_ contains C and N isotope values for cryptobenthic fishes and invertebrates:
- `ID` Sample ID
- `Taxon` Cryptobenthic fish or invertebrate
- `Weight_N` Nitrogen sample weight
- `N15` Measure of the ratio of the two stable isotopes of nitrogen, 15N:14N (‰)
- `PercentN` Elemental nitrogen content of the sample
- `Weight_C` Carbon sample weight
- `C13` Measure of the ratio of the two stable isotopes of carbon, 13C:12C (‰)
- `PercentC` Elemental carbon content of the sample
- `QC_N` / `QC_C` Quality control for nitrogen and carbon respectively
- `CN` Carbon to nitrogen ratio
- `L` Lipid content
- `C13_LF` Lipid-free C13 value following the McConnaughey & McRoy model (1979)

* UVC datasets

The dataset _CHA23_UVC_data.csv_ corresponds to underwater surveys of visually conspicuous fishes, and contains the following variables:
- `Year` Sampling year. Only 2021 and 2023 are used in the analysis
- `Atoll`
- `Island`
- `Treatment` Seabird-rich (Birdy) or rat-infested (Ratty)
- `Transect` Transect number
- `Area` Transect area
- `Species` Genus and species
- `Length` Total length
- `Family`
- `Diet` feeding group
- `a`
- `b`
- `Weight` Weight calculated with a and b (g)
- `Weight_m` Weight standardized by transect area (g/m2)

The dataset _UVC_priors.csv_ corresponds to data from Benkwitt et al. (2019) from 2015, 2018 and 2019. 

The datasets _CHA23_UVC_traits.csv_ containing Diet and Position traits and _DS2.csv_ (supplemental file with Kmax data from Morais & Bellwood 2019) were used to calculate productivity.

* Trophic discrimination factors

The table _discr.csv_ corresponds to TDFs for C and N isotopes (Post, 2002).

### 2.3 Code description

The _seabirds_cryptofauna.Rmd_ code is formatted in Rmarkdown and contains all R-based analyses and code to reproduce data and figures from the paper, including supplementary material. 
It is divided into three sections that follow the order of analyses and figures from the manuscript:

* I. Stable isotope analysis
   - I. 1. d15N
   - I. 2. Isotopic niche
* II. Community analyses
   - II. 1. Density and biomass
   - II. 2. RDA
   - II. 3. Simper
* III. Higher trophic levels
   - III. 1. Mixing models
   - III. 2. UVC


## 3. Reproducibility parameters

```R
R version 4.5.0 (2025-04-11 ucrt)
Platform: x86_64-w64-mingw32/x64
Running under: Windows 10 x64 (build 19045)

Matrix products: default
  LAPACK version 3.12.1

locale:
[1] LC_COLLATE=English_United Kingdom.utf8  LC_CTYPE=English_United Kingdom.utf8    LC_MONETARY=English_United Kingdom.utf8
[4] LC_NUMERIC=C                            LC_TIME=English_United Kingdom.utf8    

time zone: Europe/London
tzcode source: internal

attached base packages:
[1] grid      stats     graphics  grDevices utils     datasets  methods   base     

other attached packages:
 [1] lubridate_1.9.4     forcats_1.0.0       stringr_1.5.1       purrr_1.0.4         readr_2.1.5         tidyr_1.3.1        
 [7] tibble_3.3.0        tidyverse_2.0.0     dplyr_1.1.4         magick_2.8.6        ggimage_0.3.3       ggridges_0.5.6     
[13] patchwork_1.3.1     MixSIAR_3.1.12      modelr_0.1.11       emmeans_1.11.1      tidybayes_3.0.7     ggdist_3.3.3       
[19] brms_2.22.0         Rcpp_1.0.14         reshape2_1.4.4      ggrepel_0.9.6       vegan_2.6-10        lattice_0.22-7     
[25] permute_0.9-7       labdsv_2.1-0        mgcv_1.9-3          nlme_3.1-168        scales_1.4.0        ggcheck_0.0.5      
[31] ggord_1.1.8         ggpubr_0.6.0        ggplot2_3.5.2       SIBER_2.1.9         gridExtra_2.3       ggspatial_1.1.9    
[37] raster_3.6-32       sp_2.2-0            rnaturalearth_1.0.1 stars_0.6-8         abind_1.4-8         sf_1.0-21          
[43] Rlab_4.0            simcausal_0.5.7     tidytable_0.11.2    plyr_1.8.9         
```   
