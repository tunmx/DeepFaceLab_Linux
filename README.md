## Using
## 1. Prepare

Please maintain the same project directory structure as the original DeepFaceLab. Replace the DeepFaceLab directory with the project provided by us. Apart from the training scripts, other scripts are carried over from the original project, except for the newly added scripts with a “**_Pth**” suffix in the scripts directory.

```bash
└── DeepFaceLab_Linux
    ├── DeepFaceLab
    ├── README.md
    ├── scripts
    └── workspace
```

In the `workspace/model` directory, you need to place the PyTorch version of the deepfake model and its configuration, maintaining the correct directory structure:

```
├── ckpts
│   ├── decoder_124000.pth
│   ├── encoder_124000.pth
│   ├── inter_AB_124000.pth
│   └── inter_B_124000.pth
└── config.py
```

The rest of the functions such as detection, extraction, segmentation, etc., can be performed using the original scripts found in the scripts directory.

## 2. Install

On the basis of ensuring the environment of the original version (TF), add the following PyTorch version related environments:

```bash
pip install torch==1.12.0+cu116 torchvision==0.13.0+cu116 --extra-index-url https://download.pytorch.org/whl/cu116
pip install adabelief-pytorch==0.2.1 torchsummaryX==1.3.0 opencv-python==4.5.5.64 matplotlib==3.5.1 tensorboard==2.0.0 tqdm==4.66.1 grpcio-tools==1.44.0 scipy==1.8.0 numexpr==2.8.6 numpy==1.20.3 pandas==1.4.1 pillow==9.0.1
```

## 3. Run Merge

Before executing the merge, please ensure that you have completed the above steps and prepared the data you need. You can execute `7_merge_Quick_Pth.sh` or `7_merge_SAEHD_Pth.sh` to perform the merge. The interactive operation steps during the merge process are consistent with those of the original version.

```bash
bash 7_merge_Quick_Pth.sh
# or
bash 7_merge_SAEHD_Pth.sh
```

Please note that during execution, you may receive a “**No saved models found**” message. There is no need to worry, as this is an essential step in preserving parts of the original TF model. Our modified program relies on part of it, so you can simply ignore this message and continue with the next step.
