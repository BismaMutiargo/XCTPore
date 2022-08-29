# XCTPore
Public database containing images and mask pair of X-ray CT slices


The dataset is stored in a Google Cloud Bucket and can be downloaded with the instructions from Annex A. The Bucket contains files like MA001_train, MA001_mask, MA002_train, MA002_mask …. TC002_train, TC002_mask. Each file is a .npy file and can be loaded with the np.save function. 
Each .npy file has either a “_train” or “_mask” suffix and the class it belongs to is written as it’s prefix. Files with “_train” suffix contains the training images in a (300, h, w) uint16 NumPy array. The bit-depth of each pixel is 16-bits (uint16). 
Files with “_mask” contains the mask for the training image in a (300, h, w) uint8 NumPy array. The mask at index i represents the mask for ith training image in the training data. The mask is segmented in the following format:
0 – Foreground
1 – Material
2 – Pore
For Example, a file named “MA001_train” means it is the training image for class MA001. The corresponding mask can be found in the file named “MA001_mask”


