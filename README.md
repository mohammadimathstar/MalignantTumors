# MalignantTumors (in progress)
goal: detect malignant tumors inside CT scan images
### data set
the data set can be downloaded from the following link: 
https://luna16.grand-challenge.org/download

After registeration and logging in, you can use Zenodo link to go to the download page. You need to download the following files:

a) candidates.csv
b) annotations.csv
c) subset*.zip

For the subset*.zip you can pick any number between 0 to 9.

### Procedure
A five-steps procedure to detect malignant tumors inside CT scan images:

1) Load: put raw data into a form usable by PyTorch.
2) Segmentation: find voxels of interest. It helps to only focus on area of potential tumors.
3) Clustering: groups the extracted voxels into lumps, i.e. candidate nodules. Each nodules is located by the index, row and columns of its center point.
4) classify candidate nodules using CNN: actual nodules vs. non-nodules.
5) Diagnose the patient using the combined per-nodule classification (benign vs. malignant). We take the maximum of the per-tumor malignancy preditions, as only one tumor needs to be malignant for a patient to have cancer.

