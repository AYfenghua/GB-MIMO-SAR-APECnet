# GB-MIMO-SAR-APECnet
This is the data source and code regarding the use of the neural network (APECnet) to correct the amplitude-phase error problem existing in the ground-based MIMO SAR system.

## The source and construction of the dataset
Eight RAW SAR images are acquired from https://asf.alaska.edu/. The data can be easily obtained by searching the scene name (ALPSRP020160970, ALPSRP054200670, ALPSRP103336310, ALPSRP110940620, ALPSRP115120970, ALPSRP268560540, ALPSRP269950430, ALPSRP273680670) in https://search.asf.alaska.edu/. 

Select a data block of size 8192×8192 from the image as the original image data. According to the method described in the paper, each scene image is divided into 2048 original sub-images of size 128×256. Randomly select 1600 of these sub-images as the source of the data set. Apply 10 groups of random amplitude-phase errors to the orientation dimension of the sub-images, and obtain an original defocus data set of size 8×16000×128×256.

The format of the dataset is in the.h5 format, which is a commonly used data format. In each scene dataset, there are three key data: one represents the amplitude error(gain_error), another represents the phase error(phase_error), both with a size of 16000×24, indicating the amplitude and phase error values of the actual channels corresponding to 16000 defocused images; the last data represents the image data(unfocus_img), with a size of 16000×128×256×2, representing 16000 image data with a size of 128×256, presented in real part and imaginary part.

Due to the large size of the dataset and the confidentiality of the content, only the data sets of the first three scenarios have been uploaded at present. The complete dataset and the code will be uploaded after the paper is published. The data link can be accessed at:

## Specific parameters of MIMO radar
In the design and generalization experiments, the specific parameters of the MIMO radar we adopted are as follows: 
| parameters         | target       |
| ------------ | ---------- |
| carrier frequency         | 24GHz      |
| bandwidth         | 200MHz     |
| detection distance     | 2000m      |
| detection range | -45°～45° |
| transmission channels   | 16         |
| reception channels   | 8          |
| virtual channels | 128       |
| range resolution | 0.6m     |
| azimuth resolution | 0.78°     |
