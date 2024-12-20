# 02456-MonoDepth
Deep Learning Project at Denmark Technical University

# Data Preparation

After downloading the files from [Google Drive Folder](https://drive.google.com/drive/folders/1KnCH5kqMhINZyEB2M6b4LjMXrbQdu-bM?usp=sharing) arrange them in the following structure:

```
02456-MonoDepth/
├── DepthAnything_MySet/
├── DepthAnything_vkitti2/
├── Zoe_MySet/
├── Zoe_MySet_vkitti2/
├── KITTI/
├── VirtualKITTI_2/
├── Zoe_MySet_vkitti2/
├── EvalSetMetrics.ipynb
├── EvalSetMetricsVirtual.ipynb
├── util_parse_3d_dataset.py
├── README.md
```

# Predictions

## ZoeDepth 

ZoeDepth predictions are obtained using the [repo](https://github.com/isl-org/ZoeDepth).

```bash
python evaluate.py -m zoedepth_nk -d <kitti | vkitti2>
```

## DepthAnything

DepthAnything predictions are obtained using the [repo](https://github.com/isl-org/ZoeDepth).

```bash
python evaluate.py -m zoedepth --pretrained_resource="local::./checkpoints/depth_anything_metric_depth_outdoor.pt" -d <kitti | vkitti2>
```

# Training

## ZoeDepth 

ZoeDepth is trained 

```bash
python train_mono.py -m zoedepth -d <nyu | kitti> --pretrained_resource=""
```

Training logs can be found [here](https://drive.google.com/file/d/1faqzq1QA3CgQhkjZNOpZPK8Fk85LvhhK/view?usp=sharing), further more wandb platform is used for detailed logging during training [here](https://wandb.ai/ml-ops-02476/MonoDepth3-vkitti2?nw=nwuserhhotait420)

<iframe src="https://wandb.ai/ml-ops-02476/MonoDepth3-vkitti2/reports/Training-Report--VmlldzoxMDY3ODYyOA" style="border:none;height:1024px;width:100%">