The ADNI data are publicly available from http://adni.loni.usc.edu/ (registration is needed). However, diffusion tensors need to be calculated by following the instructions below.

* Data preprocessing

1) Follow the instructions in https://github.com/linulysses/iRFDA-sparse to prepare the diffusion tensors. This will create a MATLAB data file hippo.mat that contains the diffusion tensors, as well as the corresponding ID of the images from which the tensors are derived.

2) Use the subject-list.txt in https://github.com/linulysses/iRFDA-sparse to obtain some meta information about the images and subjects, such as whether a subject is cogntitively normal (CN) or has developed the Alzheimer's disease (AD).

* Analysis

Now call the script "extrinsic analysis-script.R" to analyze the data and "extrinsic plot.R" to generate the plots