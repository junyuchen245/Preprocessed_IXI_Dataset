# Preprocessed IXI Dataset
<a rel="license" href="http://creativecommons.org/licenses/by-sa/3.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/3.0/88x31.png" /></a>

<img src="https://github.com/junyuchen245/Preprocessed_IXI_Dataset/blob/main/IXI_dataset.jpg" width="1000"/>
:exclamation: Our preprocessed IXI dataset is made available under the <a rel="license" href="http://creativecommons.org/licenses/by-sa/3.0/">Creative Commons Attribution-ShareAlike 3.0 Unported License</a>. If you use this dataset, you should acknowledge the TransMorph paper:

    @article{chen2021transmorph,
    title={TransMorph: Transformer for unsupervised medical image registration},
    author={Chen, Junyu and Du, Yong and He, Yufan and Segars, William P and Li, Ye and Frey, Eric C},
    journal={arXiv preprint arXiv:2111.10480},
    year={2021}
    }

**and** acknowledge the source of the IXI data: https://brain-development.org/ixi-dataset/ 
## About the Dataset
This repository contains a preprocessed IXI brain MRI dataset (https://brain-development.org/ixi-dataset/) used in [TransMorph](https://github.com/junyuchen245/TransMorph_Transformer_for_Medical_Image_Registration).

- ***Preprocessing:*** The IXI dataset was preprocessed (e.g., skull stripping, affine alignment, and subcortical segmentation) by using [FreeSurfer](https://surfer.nmr.mgh.harvard.edu/fswiki). The steps we used are listed here - <a href="https://github.com/junyuchen245/Preprocessed_IXI_Dataset/blob/main/PreprocessingMRI.md">Brain MRI preprocessing and subcortical segmentation using FreeSurfer</a>
- ***Train-Val-Test split:*** There are **576** brain MRI volumes in total. We split the dataset into a ratio of **7:1:2**, where **403** for training (`IXI_data/Train/`), **58** for validation (`IXI_data/Val/`), and **115** for testing (`IXI_data/Test/`).
- ***Atlas image:*** Additionally, there is one atlas MRI volume and its corresponding subcortical segmentation (`IXI_data/altas.pkl`). This atlas volume was obtained from [CycleMorph](https://github.com/boahK/MEDIA_CycleMorph).
- ***File format:*** Each `.pkl` file contains a T1 weighted brain MRI and its corresponding subcortical segmentation. You can read `.pkl` file in python by doing:
  ```python
  import pickle
  def pkload(fname):
      with open(fname, 'rb') as f:
          return pickle.load(f)

  image, label = pkload("image.pkl")
  # image: a preprocessed T1-weighted brain MRI volume. Shape: 160 x 192 x 224 Intensity: [0,1]
  # label: the corresponding subcortical segmentations. Shape: 160 x 192 x 224
  ```
- ***Label map:*** A description of each label and the corresponding indexing value is provided [here](https://github.com/junyuchen245/Preprocessed_IXI_Dataset/blob/main/label_info.txt).
- ***Image size:*** Each image and label map has a size of `160 x 192 x 224`.
- ***Normalization:*** The intensity values of each image volume are normalized into a range `[0,1]`.
## Download [<img src="https://github.com/junyuchen245/junyuchen245.github.io/blob/master/images/down_arrow.gif" width="30px">](https://drive.google.com/uc?export=download&id=1-VQewCVNj5eTtc3eQGhTM2yXBQmgm8Ol)
[Download Dataset from Google Drive (1.44G)](https://drive.google.com/uc?export=download&id=1-VQewCVNj5eTtc3eQGhTM2yXBQmgm8Ol)

## Atals-to-Patient Registration
Please visit https://github.com/junyuchen245/TransMorph_Transformer_for_Medical_Image_Registration/blob/main/TransMorph_on_IXI.md for instructions on network training, inference, and evaluation using this dataset.

### <a href="https://junyuchen245.github.io"> About Me</a>

