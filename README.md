# BTS: A Bi-lingual Benchmark for Text Segmentation in the Wild

This is the repo to host the dataset BTS from the following paper:

[Xixi Xu](), [Zhongang Qi](), [Jianqi Ma](https://github.com/mjq11302010044/), [Honglun Zhang](), [Ying Shan](), [Xiaohu Qie](), **BTS: A Bi-lingual Benchmark for Text Segmentation in the Wild**

**Our dataset is now fully released for academic use.** 
To download the dataset, please send a request email to *15821795091@163.com* to get an agreement and sign.
After verifying your request, we will provide the download link for you.

## Abstract

## Selection of scenes. 
The key motivation of the selection of scenes is to ensure the representation and generalization of the dataset. 
First, we have images indoor and outdoor to balance the lighting conditions. 
Second, the text line appearance variety is also an important factor to be considered, i.e., 
text line in different orientation (vertical and horizontal text in couplets and textbooks) and 
curve-shaped (some of the signboards). The third factor lies in the font diversity, e.g., 
we have text images in printed font in textbook and artistic font on the signboard. 
We believe that varieties in these three perspectives can ensure the segmentation model 
to be well-trained with better generalization.

<p align="center">
  <img src=".figure/BTS_examples.png" width="99%">
</p>

### Dataset annotation.
BTS eliminate algorithms or out-of-the-box models for the labeling process to prevent some bad labeling cases. 
The annotation workflow is as follows.

(1) Images cleaning. Unqualified examples such as fuzzy images with unrecognizable characters and strokes will be filtered out.

(2) Manual annotation. All the images in BTS are manually annotated by humans in three levels, 
including the pixel-level, the character-level, and the line-level annotations. 
PhotoShop is the main tool. The pencil tool in Photoshop is utilized to assist the annotators 
to label pixel-level mask annotations for texts.  

(3) Two rounds of quality checks. 
During the labeling process, annotators will cross check the annotations from each other; 
after the labeling process, several professional researchers will double check the annotations. 

The designed workflow ensures all annotations to be made in relatively high quality and benchmark to be highly-reliable.

<p align="center">
  <img src=".figure/anno.bmp" width="99%">
</p>

### Dataset statistics.


### Download

Our dataset (TextSeg) is academia-only and cannot be used on any commercial project and research. To download the data, please send a request email to *textseg.dataset@gmail.com* and tell us which school you are affiliated with. 

A full download should contain these files:

* ```image.tar.gz``` contains 4024 images.
* ```annotation.tar.gz``` labels corresponding to the images. These three types of files are included:
  * ```[dataID]_anno.json``` contains all word- and character-level translations and bounding polygons.
  * ```[dataID]_mask.png``` contains all character masks. Character mask label value will be ordered from 1 to n. Label value 0 means background, 255 means ignore. 
  * ```[dataID]_maskeff.png``` contains all character masks **with effect**. 
  * ```Adobe_Research_License_TextSeg.txt``` license file.
* ```semantic_label.tar.gz``` contains all word-level (semantic-level) masks. It contains:
  * ```[dataID]_maskfg.png``` 0 means background, 100 means word, 200 means word-effect, 255 means ignore. (The ```[dataID]_maskfg.png``` can also be generated using ```[dataID]_mask.png``` and ```[dataID]_maskeff.png```)
* ```split.json``` the official split of train, val and test.
* [Optional] ```semantic_label_v1.tar.gz``` the old version of label that was used in our paper. One can download it to reproduce our paper results.


In this table, we compare BTS with a variety of representative datasets. 

<font size="11" face="Courier New">
<table>
  <tr>
    <td colspan="2">Dataset</td>
    <td colspan="2">Text Type</td>
    <td colspan="2">Images</td>
    <td colspan="2">Words</td>
    <td colspan="2">Chars</td>
    <td colspan="2">Masks</td>
    <td colspan="2">Char Classes</td>
    <td colspan="2">Language</td>
  </tr>
  <tr>
    <td>ICDAR13 FST</td>
    <td>Scene</td>
    <td>462</td>
    <td>1944</td>
    <td>6620</td>
    <td>Word,Char</td>
    <td>36</td>
    <td>English</td>
  </tr>
  <tr>
    <td>COCO_TS</td>
    <td>Scene</td>
    <td>14690</td>
    <td>139034</td>
    <td>-</td>
    <td>Word</td>
    <td>36</td>
    <td>English</td>
  </tr>
  <tr>
    <td>MLT_S</td>
    <td>Scene</td>
    <td>6896</td>
    <td>30691</td>
    <td>-</td>
    <td>Word</td>
    <td>36</td>
    <td>English</td>
  </tr>
  <tr>
    <td>Total-Text</td>
    <td>Scene</td>
    <td>1555</td>
    <td>9330</td>
    <td>-</td>
    <td>Word</td>
    <td>36</td>
    <td>English</td>
  </tr>
  <tr>
    <td>TextSeg</td>
    <td>Scene+Design</td>
    <td>4024</td>
    <td>15691</td>
    <td>73790</td>
    <td>Word,Word-Effect,Char</td>
    <td>36</td>
    <td>English</td>
  </tr>
  <tr>
    <td><b>BTS(Ours)</b></td>
    <td>Scene</td>
    <td>14287</td>
    <td>462</td>
    <td>462</td>
    <td>462</td>
    <td>462</td>
    <td>462</td>
  </tr>
</table>
</font>


## Acknowledgements

The directory `.\hrnet_code` is directly copied from the HRNet official github website [(link)](https://github.com/HRNet/HRNet-Semantic-Segmentation). HRNet code ownership should be credited to HRNet authors, and users should follow their terms of usage. 

