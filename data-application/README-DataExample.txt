The ADNI data are publicly available from http://adni.loni.usc.edu/ (registration is needed). However, diffusion tensors need to be calculated by following the instructions below.

* Data preprocessing

1) Follow the instructions in https://github.com/linulysses/iRFDA-sparse to prepare the diffusion tensors. This will create a MATLAB data file hippo.mat that contains the diffusion tensors, as well as the corresponding ID of the images from which the tensors are derived.

2) Use the subject-list.txt in https://github.com/linulysses/iRFDA-sparse to obtain some meta information about the images and subjects, such as whether a subject is cogntitively normal (CN) or has developed the Alzheimer's disease (AD).

* Combine meta information with diffusion tensors

Suppose the meta information is stored in a data frame called 'meta' with three columns: a column of 'image_id', a column of 'subject_id', and a column of 'group' (CN or AD). Use the following R commands to combine the tensors with metadata:

library(R.matlab)
hippo.mat <- readMat('hippo.mat')
idx <- match(hippo.mat$imageIds,meta$image_id)
dti=hippo.mat$dti.result
metatinfo=meta[idx,]
save(file='hippo.RData', dti, metatinfo)

* Analysis

Now call the script analysis-script.R to analyze the data and plot.R to generate the plots