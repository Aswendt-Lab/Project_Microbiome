# Project_Microbiome
Project repository rs-fMRI of germfree and naïve mice with/without cortical stroke 

## Step-by-Step guide to replicate the analysis

1. Install [AIDAmri](https://github.com/aswendtlab/AIDAmri) and [AIDAconnect](https://github.com/aswendtlab/AIDAconnect)

2. Download MRI raw and processed data (raw_data/proc_data) from [G-Node](https://doi.org/10.12751/g-node.699mgv)
!!in the data repository you will find the AIDAmri and AIDAconnect versions used for analysis - this way you save time with pre-set input parameters to reproduce all steps!!

3. Run AIDAmri pre- and postprocessing steps for T2 and DTI data, see [manual](https://github.com/aswendtlab/AIDAmri/blob/master/manual.pdf)

4. Extract the graph theoretical measures using AIDAconnect and Matlab
4.1 * 1) Load the data and generate the graphs``` mergeDTIdata_input.m)```
4.2
  
