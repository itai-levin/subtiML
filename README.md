# subtiML

## Raw Data
Expression data:
- Table S2 from "Condition-dependent transcriptome reveals high-level regulatory architecture in Bacillus subtilis" (Nicolas, Mäder, Dervyn et al., submitted). Stored as `expression_data.xlsx`.
Genome sequence: 
- Bacillus subtilis subsp. subtilis str. 168 genome sequence downloaded from NCBI, reference NC_000964.3. Stored as `bsubt168.fna`.

## Data Processing
To generate the cleaned dataset, click through the jupyter notebook `data processing.ipynb`
The notebook performs the following processing steps:

- Retrieve the sequences for the regions 20, 50, and 100bp upstream of each gene
- Compute the mean expression level across different replicates for the same conditions
- For each gene, store all of the expression data in a single array
- For each gene, also compute a normalized (z-scored) array of expression data
- Store all this data in `cleaned_data.csv`
- Store the order of the conditions stored in the expression array in `experiments_order.txt`

