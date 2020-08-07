## Comparison of TARA ASVs and MAGs

### ASV table download source:
* de Vargas, C., Audic, S., Henry, N., Decelle, J., Mahé, F., Logares, R., … Karsenti, E. (2015, May 22). First Tara Oceans V9 rDNA metabarcoding dataset. Zenodo. http://doi.org/10.5281/zenodo.15600
* Benjamin Callahan. (2017). ASV Tables inferred by DADA2 from the TARA Oceans v9 metabarcoding dataset [Data set]. Zenodo. http://doi.org/10.5281/zenodo.581694 

Data originates from de Vargas et al. 2015, ASVs were generated from ~766 million reads from 334 samples. ASVs processed here are a result of concensus chimera removal.

### Taxonomy assignment with DADA2

Using dada2 and PR2 database (v4.12)
```
# Load R v3.6.1
library("dada2")

# Import Tara V9 seq table
tara <- readRDS("st.consensus.rds")

# Assign taxonomy
tara_tax <- assignTaxonomy(tara, "/vortexfs1/omics/huber/shu/db/pr2-db/pr2_version_4.12.0_18S_dada2.fasta.gz", taxLevels = c("Kingdom","Supergroup","Division","Class","Order","Family","Genus","Species"), multithread = TRUE)

```

