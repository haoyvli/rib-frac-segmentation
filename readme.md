# FracNet

## Code Structure
* FracNet/
    * [`dataset/`](./dataset): PyTorch dataset and transforms.
    * [`models/`](./models): PyTorch 3D-UNet model and losses.
    * [`prediction_directory/`](./prediction_directory): where the segmentation results of  fractured ribs are stored.
    * [`utils/`](./utils): Utility functions.
    * [`main.py`](main.py): Training script.
    * [`predict.py`](predict.py): post-processing and generating predictions.
    * [`model_weights.pth`](model_weights.pth): the model we derived by training with 3D-UNet.

## Requirements
```
SimpleITK==1.2.4
fastai==1.0.59
fastprogress==0.1.21
matplotlib==3.1.3
nibabel==3.0.0
numpy>=1.18.5
pandas>=0.25.3
scikit-image==0.16.2
torch==1.4.0
tqdm==4.38.0
```

## Usage

### Training
To train the FracNet model, run the following in command line:
```bash
!python -m main --train_image_dir <train_image_directory> --train_label_dir <train_label_directory> --val_image_dir <val_image_directory> --val_label_dir <val_label_directory> --save_model <True or False>
```

### Prediction
To generate prediction, run the following in command line:
```bash
python -m predict --image_dir <image_directory> --pred_dir <predition_directory> --model_path <model_weight_path>
```

### Note

Due to the copyright of the raw dataset, we do not post it on Github, nor the segmentation results of it.

