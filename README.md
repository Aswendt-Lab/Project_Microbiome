# Project_Microbiome
Project repository rs-fMRI of germfree and naïve mice with/without cortical stroke. 
The aim of this study was to characterize the effect of the gut microbiota in mice with experimental stroke using functional connectivity analysis. 

## Step-by-Step guide to replicate the analysis

1. Install [AIDAmri](https://github.com/aswendtlab/AIDAmri) and [AIDAconnect](https://github.com/aswendtlab/AIDAconnect)

2. Download MRI raw and processed data (raw_data/proc_data) from [G-Node](https://doi.org/10.12751/g-node.699mgv)
!!in the data repository you will find the AIDAmri and AIDAconnect versions used for analysis - this way you save time with pre-set input parameters to reproduce all steps!!

3. Run AIDAmri pre- and postprocessing steps for T2 and DTI data, see [manual](https://github.com/aswendtlab/AIDAmri/blob/master/manual.pdf)

4. Extract the graph theoretical measures using AIDAconnect and Matlab
   1. Load the data and generate the graphs``` mergeDTIdata_input.m```
   2. To generate matrices use ```plotCorrelationMatrices.m``` (a full list of the atlas labels can be found [here](https://github.com/aswendtlab/AIDAconnect/blob/master/Tools/infoData/acronyms_splitted.mat)
   3. To generate matrices use ```plotCorrelationMatrices.m```
   4. To generate the histogram plots (frequency of degree/node strength) use ```plotDistribution.m```
   5. To generate the total degree/node strength plots (group difference needs to be calculated separately) use ```compareTotalStrength.m```, ```compareTotalDegree.m```
   6. 


  
