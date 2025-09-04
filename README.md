# GB-MIMO-SAR-APECnet
This is the data source and code regarding the use of the neural network (APECnet) to correct the amplitude-phase error problem existing in the ground-based MIMO SAR system.

## Source of the dataset
Eight RAW SAR images are acquired from https://asf.alaska.edu/. The data can be easily obtained by searching the scene name (ALPSRP020160970, ALPSRP054200670, ALPSRP103336310, ALPSRP110940620, ALPSRP115120970, ALPSRP268560540, ALPSRP269950430, ALPSRP273680670) in https://search.asf.alaska.edu/. 

An 8192×8192-sized data block was selected from the image as the original image data. According to the method described in the paper, it was divided into 2048 original sub-images with a size of 128×256. Ten sets of random amplitude-phase errors were applied to the orientation dimension of the sub-images, resulting in a defocus data set of 8×20480×128×256.
