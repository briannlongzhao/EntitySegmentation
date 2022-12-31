# EntitySegmentation

Open-world image segmentation. Original repo: https://github.com/dvlab-research/Entity

## Install Prerequisites

```bash
# Install PyTorch 1.10.0 with CUDA 11.3
conda install pytorch==1.10.0 torchvision==0.11.0 torchaudio==0.10.0 cudatoolkit=11.3 -c pytorch -c conda-forge

# Install Detectron2 with PyTorch 1.10.0 and CUDA 11.3
python -m pip install detectron2 -f https://dl.fbaipublicfiles.com/detectron2/wheels/cu113/torch1.10/index.html

# Install other prerequisites
pip install -r requirements.txt
```

## Run Inference

```bash
python demo_result_and_vis.py \
--config-file configs/entity_r101_1x.yaml \
--input /path/to/input_dir \
--output /path/to/output_dir \
MODEL.WEIGHTS /path/to/model/weights \
MODEL.CONDINST.MASK_BRANCH.USE_MASK_RESCORE "False"
```

`--input` is the path to image input directory and should contain images only, such as `JPEGImages/` in Pascal VOC dataset or `train2017/` in COCO dataset.

`--output` specifies an output directory, for each image in input directory, the program will save a visualization of the segmentation result and a corresponding `.npy` mask of the segmentation result.

