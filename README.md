# SpineNet-Pytorch
SpineNet is a CVPR 2020 paper for object detection. This project is a kind of implementation of SpineNet using mmdetection.

It is based on the

* the paper [SpineNet: Learning Scale-Permuted Backbone for Recognition and Localization](https://arxiv.org/abs/1912.05027)
* [official TensorFlow implementation](https://github.com/tensorflow/tpu/tree/master/models/official/detection)

## Models

| Variant      | mAP  | Params | FLOPs   | mAP in paper | Params in paper | FLOPs in paper |
| ------------ | ---- | ------ | ------- | ------------ | --------------- | -------------- |
| SpineNet-49S | 39.1 | 11.15M | 30.04B  | 39.9         | 12.0M           | 33.8B          |
| SpineNet-49  | 42.7 | 28.31M | 83.7B   | 42.8         | 28.5M           | 85.4B          |
| SpineNet-96  | ——   | 42.74M | 261.35B | 47.1         | 43.0M           | 265.4B         |
| SpineNet-143 | ——   | ——     | ——      | 48.1         | 66.9M           | 524.4B         |
| SpineNet-190 | ——   | ——     | ——      | ——           | 163.6M          | 1885B          |

**Note**: The parameters and flops are a little different from paper, so I think there are some difference between my code and official's code. More information about models can see in [MODEL_DETAILS.md](MODEL_DETAILS.md)

## Usage

1. **Install mmdetection**

   This implementation is based on [mmdetection](https://github.com/open-mmlab/mmdetection)(v1.1.0+8732ed9). Please refer to [INSTALL.md](docs/INSTALL.md) for installation and dataset preparation.

2. **Copy the codes to mmdetection directory**

   ```shell
   cp -r mmdet/ ${MMDETECTION_PATH}/
   cp -r configs/ ${MMDETECTION_PATH}/
   ```

 3. **Prepare data**

     The directories should be arranged like this:
     
        >   mmdetection
        >     ├── mmdet
        >     ├── tools
        >     ├── configs
        >     ├── data
        >     │   ├── coco
        >     │   │   ├── annotations
        >     │   │   ├── train2017
        >     │   │   ├── val2017
        >     │   │   ├── test2017


 4. **Train D0 with 4 GPUs**

    ```shell
    CONFIG_FILE=configs/spinenet/spinenet_49_B_8gpu.py
    ./ tools/dist_train.py ${CONFIG_FILE} 4
    ```

 5. **Calculate parameters and flops**

     ```shell
      python tools/get_flops.py ${CONFIG_FILE} --shape $SIZE $SIZE
     ```

6. **Test**

   ```shell
   python tools/test.py ${CONFIG_FILE} ${CHECKPOINT_FILE} --out  ${OUTPUT_FILE} --eval bbox
   ```

More usages can reference [mmdetection documentation](https://mmdetection.readthedocs.io/en/latest/GETTING_STARTED.html#inference-with-pretrained-models).

## Update log

- [2020-05-30] Add SpineNet-49S results.
- [2020-05-13] Update codes and results.
- [2020-05-02] Create this repository.



