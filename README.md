# Light Field Messaging with Deep Photographic Steganography
Published in CVPR 2019
by Eric Wengrowski and Kristin Dana

Paper link: 
http://openaccess.thecvf.com/content_CVPR_2019/html/Wengrowski_Light_Field_Messaging_With_Deep_Photographic_Steganography_CVPR_2019_paper.html


# Code and CDTF 1M dataset:
The code and data is only available for academic, non-commercial use.
Please follow this link to obtain a free license and download:
http://license.rutgers.edu/technologies/2019-113_novel-light-field-messaging-captured-in-a-camera

If you encounter a download error from Google, please try this:
1. Copy the Publicly shared Camera1M file into your own google drive. You can do that by clicking on top and "copy to my drive" button. 
2. You'll need an upgraded Google Drive account to do that because the basic account has a limitation of 10GB. So upgrade the Google account or find an account that has 2 TB free on it. 
3. Once you have copied in your drive you can easily download it without any issues because it's in your drive now. 


# Code:
This code is written for Python 3.6 using the Conda environment manager.
NOTE: This code will NOT WORK with versions of PyTorch 0.4.0 and beyond.
Previous versions of PyTorch can be downloaded here: https://pytorch.org/get-started/previous-versions/

OS: Ubuntu 16.04

Python Dependencies:
```
pytorch 0.3.0
torchvision
cv2 (OpenCV)
matplatlib
pil
```

Other Standard Python Libraries needed:
```
os
time
numpy
argparse
glob
pickle
collections
```

Train a CDTF function:
```
$ python main.py cdtf --epoch 2 --image-dataset </path/to/cdtf_measurements/cdtf_matches/camera_captured/> --target-dataset </path/to/cdtf_measurements/cdtf_matches/ground_truth/> --gray 0
```

To train a steganography function:
```
$ python main.py steg --epoch 5 --batch-size 2 --log-interval 2000 --image-size 512 --message-size 512 --cdtf-model </path/to/your.model> --dataset </path/to/your/images> --message-folder </path/to/your/message/folder/.>
```

To evaluate the trained model:
```
$ python main.py steg_eval --model <./path/to/trained/model> --input-image <image_input.tiff> --input-message <message_input.tiff>
```

# Data:
Camera-Display 1M contains over 1,000,000 pairs of images. 

The images were collected from MSCOCO, rendered on a variety of electronic displays, and cpatured using a variety of cameras. 
The images are organized into 3 classes: 1. original images, 2. camera-captured images, and 3. unsorted images. 
Please use the MATLAB code provided in ```</LFM_code/dev/matlab_Image_matching_code/>``` to sort new image pairs. 
Directory names label the camera-display hardware pairs used to collect each image.


# Please cite as:
```
@inproceedings{wengrowski2019light,
  title={Light Field Messaging With Deep Photographic Steganography},
  author={Wengrowski, Eric and Dana, Kristin},
  booktitle={Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition},
  pages={1515--1524},
  year={2019}
}
```

Please report any issues to eric@steg.ai
Thank You!

Final Note: This code and data is not allowed for any commercial purpose without written concent from the authors.
