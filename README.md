# SubtiML
## 20.490 Final Project
### Itai Levin

## Raw Data
Expression data:
- Table S2 from "Condition-dependent transcriptome reveals high-level regulatory architecture in Bacillus subtilis" (Nicolas, Mäder, Dervyn et al., 2012). Stored as `expression_data.xlsx`.
Genome sequence: 
- Bacillus subtilis subsp. subtilis str. 168 genome sequence downloaded from NCBI, reference NC_000964.3. Stored as `bsubt168.fna`.
Experimental growth conditions:
- The different experimental growth conditions tested are summarized in `experiments_order.txt`. More information about what exactly the conditions correspond to can be found in the paper by Nicolas et al.

## Data Processing
To generate the cleaned dataset, click through the jupyter notebook `data processing.ipynb`
The notebook performs the following processing steps:

- Retrieve the sequences for the regions 20, 50, 100, 200, 1000bp upstream of each gene
- Compute the mean expression level across different replicates for the same conditions
- For each gene, store all of the expression data in a single array
- For each gene, also compute a normalized (z-scored) array of expression data
- Store all this data in `cleaned_data.csv`
- Store the order of the conditions stored in the expression array in `experiments_order.txt`
- Visualize correlatedness of growth conditions

## Model training
To follow the training protocol, click through the jupyter notebook `train CNN.ipynb`
Two separate training tasks were performed
- A CNN binary classification model was trained on each experimental growth condition to predict whether a given upstream DNA sequence would lead to up- or downregulation of the gene in the given growth condition
- A CNN regression model was trained to predict the full expression profile across all experimental conditions for a given upstream DNA sequence

