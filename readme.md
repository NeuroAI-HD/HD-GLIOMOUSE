# Installation instructions
## Installation requirements
hd-gliomouse only runs on Linux. You need a pytorch capable GPU with 4GB of GPU memory to run hd-gliomouse.

1) We strongly recommend you install hd-gliomouse in a separate python virtual environment. [Here is a quick how-to for Ubuntu.](https://linoxide.com/linux-how-to/setup-python-virtual-environment-ubuntu/)
2) Once you set up the environment (and activated it), install hd-gliomouse with pip: `pip install hd_gliomouse` - Done

This will install hd_gliomouse commands directly onto your system. You can use them from anywhere.

# Usage

## Run hd-gliomouse
hd-gliomouse provides two main scripts: `hd_gliomouse_predict` and `hd_gliomouse_predict_folder`.

### Predicting a single case
`hd_gliomouse_predict` can be used to predict a single image. It is useful for exploration or if the number of cases 
to be procesed is low. Here is how to use it:

`hd_gliomouse_predict -i INPUT_FILE -o OUTPUT_FILE`

INPUT_FILE and OUTPUT_FILE must be a niftis (end with .nii.gz).

### Predicting multiple cases
`hd_gliomouse_predict_folder` is useful for batch processing, especially if the number of cases to be processed is large. By 
interleaving preprocessing, inference and segmentation export we can speed up the prediction significantly. Furthermore, 
the pipeline is initialized only once for all cases, again saving a lot of computation and I/O time.  Here is how to use it:

`hd_gliomouse_predict_folder -i INPUT_FOLDER -o OUTPUT_FOLDER`

INPUT_FOLDER must contain nifti images (.nii.gz). The results will be written to the OUTPUT_FOLDER (with the same file names).
 If the output folder does not exist it will be created.