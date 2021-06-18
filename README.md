# Project_Microbiome
Project repository rs-fMRI of germfree and naïve mice with/without cortical stroke. 
The aim of this study was to characterize the effect of the gut microbiota in mice with experimental stroke using functional connectivity analysis. 

## Step-by-Step guide to replicate the analysis

1. Download MRI raw and processed data (raw_data/proc_data) from [G-Node](https://doi.org/10.12751/g-node.699mgv). The proc_data is grouped, thus GF/SPF, naive/stroke mice are grouped in the correct subfolder already. Further, we provide the AIDAmri and AIDAconnect versions used for analysis - this way you save time with pre-set input parameters to reproduce all steps!

2. Install [AIDAmri](https://github.com/aswendtlab/AIDAmri) and [AIDAconnect](https://github.com/aswendtlab/AIDAconnect). Note! Anaconda Python 3 installation and Matlab_R2018/2019 are required, see the manuals for install instructions. 

3. Run AIDAmri pre- and postprocessing steps for T2 and rs-fMRI data, see [manual](https://github.com/aswendtlab/AIDAmri/blob/master/manual.pdf). Note! To save time, you can use ```batchProc.py```. If you do not use the AIDAmri version provided together with the data set, make sure to adjust ```process_fMRI.py``` (or your tool to extract the rs-fMRI time series) with the correct repetition time ```-t 1.42``` and the frequency range ```cutOff_high_sec = 100.0 cutOff_low_sec = 12.5```.

4. Extract the graph theoretical measures using AIDAconnect and Matlab
   1. Load the data and generate the graphs``` mergeDTIdata_input.m```
   2. To generate matrices use ```plotCorrelationMatrices.m``` (a full list of the atlas labels can be found [here](https://github.com/aswendtlab/AIDAconnect/blob/master/Tools/infoData/acronyms_splitted.mat))
![image](https://user-images.githubusercontent.com/79273576/122476952-4e0f5000-cfc7-11eb-9ab4-2e0b09914eff.png)
   3. To generate the histogram plots (frequency of degree/node strength) use ```plotDistribution.m``` range 1-50 (strength), 1-100 (degree).\
![image](https://user-images.githubusercontent.com/79273576/122524317-45933580-d018-11eb-939b-06a28f2fea3e.png)
   6. To generate the total degree/node strength plots (group difference needs to be calculated separately) use ```compareTotalStrength.m```, ```compareTotalDegree.m``` The function was written for multiple time points - you can ignore this as there is only one time point (P0) in this study.\
![image](https://user-images.githubusercontent.com/79273576/122524498-7e330f00-d018-11eb-8647-3448257b5407.png)
   7. To generate the graphs with 20 top connections (ranked according to the Pearson correlation) use ```analyzeMostConnected.m```.\
![image](https://user-images.githubusercontent.com/79273576/122524945-02859200-d019-11eb-986a-582f96a085eb.png)
   8. To visualize a subnetwork of the whole brain graph use ```plotSelectedregions.m```.\
![image](https://user-images.githubusercontent.com/79273576/122526699-dff47880-d01a-11eb-8ce6-2bef58ca6309.png)
   9. To calculate global measures (e.g. density, modularity, etc.) use ```plotGlobalParameter.m```.\
![image](https://user-images.githubusercontent.com/79273576/122527429-95273080-d01b-11eb-8791-2fe36046a1eb.png)
   11. To calculate the correlation/edge weight between two regions use ```plotConnectionWeight.m``` and for all other local measures use ```plotLocalParameter.m```.\
![image](https://user-images.githubusercontent.com/79273576/122527635-c99aec80-d01b-11eb-9978-221850ca0ce2.png)
