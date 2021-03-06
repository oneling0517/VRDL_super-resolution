# VRDL_HW4 - Super resolution

## The link of my Colab

Click [My colab link](https://colab.research.google.com/drive/1mrqrHPnOH7Jx5W3o_2td_CifL7wjtpEo?usp=sharing) or just run Super resolution.ipynb

## Git clone my project
```
!git clone https://github.com/oneling0517/VRDL_HW4.git
```
## Datasets Download
You can download the datasets [here](https://drive.google.com/file/d/1GL_Rh1N-WjrvF_-YOKOyvq0zrV6TF4hb/view).
```
os.chdir("/content/VRDL_HW4")
!gdown --id '1GL_Rh1N-WjrvF_-YOKOyvq0zrV6TF4hb' --output dataset.zip

!apt-get install unzi
!unzip -q 'dataset.zip' -d dataset
```

## Data Directory
```text
+- VRDL_HW4
    +- dataset
        +- testing_lr_images
            +- testing_lr_images
                +- 00.png
                +- 01.png
                ...
                +- 13.png
        +- training_hr_images
            +- training_hr_images
                +- 2092.png
                +- 8049.png
                +- 8143.png
                ...
    datasets.py
    eval.py
    model.py
    split_train_val.py
    test.py
    train.py
    utils.py
```

## Split the training data
```
python3 split_train_val.py
```

## Training
Use SRResNet model.
```
python3 train.py
```

## Evaluation
Use the best checkpoint of the model to evaluate the PSNR.
```
python3 eval.py
```

## Testing
Use the checkpoint from [Google Drive](https://drive.google.com/file/d/1EZUKbIjzva0G7L1nVRT1OK5enQBPquwx/view?usp=sharing).
The final images will in the "result" folder.
```
os.chdir("/content/VRDL_HW4")
%mkdir models
os.chdir("/content/VRDL_HW4/models")
!gdown --id '1EZUKbIjzva0G7L1nVRT1OK5enQBPquwx' --output best_checkpoint_srresnet.pth.tar
```
```
python3 test.py
```

## Inference

You can click [here](https://colab.research.google.com/drive/1EHEAL5ENsLKIEoqerKStWYJMyqduB7aE?usp=sharing) or just run Inference.ipynb.

## Reference
https://github.com/sgrvinod/a-PyTorch-Tutorial-to-Super-Resolution.git
https://github.com/pengpaiSH/Kaggle_NCFM.git

