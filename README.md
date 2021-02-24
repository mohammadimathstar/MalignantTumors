# MalignantTumors

A five-steps procedure to detect malignant tumors inside CT scan images:

1) Load: put raw data into a form usable by PyTorch.
2) Segmentation: find voxels of interest. It helps to only focus on area of potential tumors.
3) Clustering: groups the extracted voxels into lumps, i.e. candidate nodules. Each nodules is located by the index, row and columns of its center point.
4) classify candidate nodules using CNN: actual nodules vs. non-nodules.
5) Diagnose the patient using the combined per-nodule classification (benign vs. malignant). We take the maximum of the per-tumor malignancy preditions, as only one tumor needs to be malignant for a patient to have cancer.

