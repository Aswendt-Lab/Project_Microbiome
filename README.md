# Project_Microbiome
Project repository rs-fMRI of germfree and naïve mice with/without cortical stroke. 
The aim of this study was to characterize the effect of the gut microbiota in mice with experimental stroke using functional connectivity analysis. 

## Step-by-Step guide to replicate the analysis

1. Download MRI raw and processed data (raw_data/proc_data) from [G-Node](https://doi.org/10.12751/g-node.699mgv)
!!in the data repository you will find the AIDAmri and AIDAconnect versions used for analysis - this way you save time with pre-set input parameters to reproduce all steps!!

2. Install [AIDAmri](https://github.com/aswendtlab/AIDAmri) and [AIDAconnect](https://github.com/aswendtlab/AIDAconnect). Note! Anaconda Python 3 installation and Matlab_R2018/2019 are required, see the manuals for install instructions. 

3. Run AIDAmri pre- and postprocessing steps for T2 and rs-fMRI data, see [manual](https://github.com/aswendtlab/AIDAmri/blob/master/manual.pdf). Note! To save time, you can use the batch. If you do not use the AIDAmri version provided together with the data set, make sure to adjust ```process_fMRI.py``` with the correct repetition time ```-t 1.42``` and the frequency range   ```cutOff_high_sec = 100.0 cutOff_low_sec = 12.5```

4. Extract the graph theoretical measures using AIDAconnect and Matlab
   1. Load the data and generate the graphs``` mergeDTIdata_input.m```
   2. To generate matrices use ```plotCorrelationMatrices.m``` (a full list of the atlas labels can be found [here](https://github.com/aswendtlab/AIDAconnect/blob/master/Tools/infoData/acronyms_splitted.mat)


   4. To generate matrices use ```plotCorrelationMatrices.m```
   5. To generate the histogram plots (frequency of degree/node strength) use ```plotDistribution.m```
   6. To generate the total degree/node strength plots (group difference needs to be calculated separately) use ```compareTotalStrength.m```, ```compareTotalDegree.m```
   7. 


  
