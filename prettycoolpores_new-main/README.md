## PrettyCoolPores
This repository includes code used for bioinformatics analysis and figures for project :
    **"Circadian PERIOD proteins sculpt the mammalian alternative splicing landscape"**  
    Bioarchive link: https://www.biorxiv.org/content/10.1101/2024.12.23.630108v1 

**PrettyCoolPores**    
The following scripts use the result obtained from flair transcriptome generation and salmon quantification, (earlier scripts: https://box.hu-berlin.de/d/1075d20d42334f5e916c/?p=%2Fscripts&mode=list ). Alignment done on mm39 mouse genome. Result folders used as input are: FLAIR: FLAIR_2024-09-11, salmon: salmon_2024-09-25. 

**1. Abundance of expressed transcripts per sample**  
script: abundance for suppa.R  
This R script needs:  
* transcriptome .gtf file,salmon/quantification .sf 
* files to generate three abundance no batch no log files that will be used to: Run suppa & differential suppa

**2. Generation/identification of alternative splicing events in the dataset and their quantification per sample.**   
Tool used: https://github.com/comprna/SUPPA  
script: run_suppa.sh  
Script that runs suppa taking the transcriptome and abundance per transcript to generate alternative splicing events and their quanitfication psi files.
- ioe files
- psi files
- ...

**3. Downstream analysis and figure generation**   
scripts:Figure1_2024_12_03.R,   
        Figure2_2024_12_03.R,   
        Figure3_2024_12_04,   
        fig4_1_2024_12_04,  
        fig4_2_2024_12_04,  
        Figure5_2024_12_04, 
Need to update path/for/suppa & path/for/FLAIR as per your run dat. All packages used are being loaded within the script.  

**4. Differential splicing using suppa**  
Tool used: https://github.com/comprna/SUPPA  
script: diff_suppa.sh  
To do differential splicing analysis b/w CT 20 of KO and WT  
    1.Takes expression and makes ioe files  
    2.Calculates psi  
    dpsi saved as .dpsi.temp but its not an issues and more for relative abosulte path in the codes for suppa. Discussed in their   gitlab issues if someone wants to change


**5. For productivity per transcripts**  
tool used: FLAIR (predict productivity) https://flair.readthedocs.io/en/latest/  
script: prodc.sh  
makes extended gtf file, changes it to bed12 and to run predict productivity in flair. Needs flair, gtftogenepred and genepredtobed installed or in an environemnt. It might need to be run with some changes because there was a problem installing three of the tools together in one envs. Can be run as separate command sto get the same results.  

**Note**: Scripts to be run from the script folder as most follow relative paths for uploading files  
> For detailed author contributions, please contact lead contact 