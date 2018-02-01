# EssNet 
(End-to-end Synthesis and Segmentation Network)

## Adversarial Synthesis Learning Enables Segmentation Without Target Modality Ground Truth

This is our ongoing PyTorch implementation for end-to-end synthesis and segmentation without groudtruth.
The paper can be found in [arXiv](https://arxiv.org/abs/1712.07695) for ISBI 2018

The code was written by [Yuankai Huo](https://sites.google.com/site/yuankaihuo/) and developed upon [CycleGAN Torch](https://github.com/junyanz/CycleGAN).


<img src='imgs/Figure3.jpg' width=300>
<img src='imgs/Figure2.jpg' width=300>


If you use this code for your research, please cite:

Yuankai Huo, Zhoubing Xu, Shunxing Bao, Albert Assad, Richard G. Abramson, Bennett A. Landman. [Adversarial Synthesis Learning Enables Segmentation Without Target Modality Ground Truth.](https://arxiv.org/abs/1712.07695)  In [arXiv](https://arxiv.org/abs/1712.07695) 2017.   

## Prerequisites
- Linux or macOS
- Python 2
- CPU or NVIDIA GPU + CUDA CuDNN
- pytorch 0.2

## Training Data and Testing Data
We used MRI and CT 2D slices (from coronal view) as well as MRI segmentatons as training data.
We used CT 2D slices (from coronal view) as testing data
The data orgnization can be seen in the txt files in `sublist` directory

## Training
```bash
python train_yh.py --dataroot ./datasets/yh --name yh_cyclegan_imgandseg --batchSize 5 --model cycle_seg --pool_size 50 --no_dropout --yh_run_model Train --dataset_mode yh_seg --yh_data_model ImageWithMask --input_nc 1  --seg_norm CrossEntropy --output_nc 1 --output_nc_seg 7 --checkpoints_dir /home-local/Cycle_Deep/CheckpointsNew/checkpoints/cross_entropy_lr0_0002 --test_seg_output_dir /home-local/Cycle_Deep/Output/CycleTest_all_new/cross_entropy_lr0_0002  --display_id 0 --weight_2 10 --weight_3 10 --weight_7 10



