# MODEL DETAILS
In paper SpineNet was trained with three protocols. I only trained with protocol B. Training SpineNet takes lots of time, for example I took 7 days to train SpineNet-49 with 8 TITAN V gpus.

- protocol  A: random scale between[0.8,1.2];250 epochs;DropBlock
- protocol  B: random scale between[0.5,2.0];350 epochs
- protocol  C: random scale between[0.5,2.0];500 epochs;stochastic depth;Swish

### mAP

| Variant      | my code(B) | paper(A) | paper(B) | paper(C) |
| ------------ | ---------- | -------- | -------- | -------- |
| SpineNet-49S | 39.1       | ——       | 39.9     | 41.5     |
| SpineNet-49  | 42.7       | 40.8     | 42.8     | 44.3     |

### Details

- SpineNet-49
    ```
     Average Precision  (AP) @[ IoU=0.50:0.95 | area=   all | maxDets=100 ] = 0.427
     Average Precision  (AP) @[ IoU=0.50      | area=   all | maxDets=100 ] = 0.627
     Average Precision  (AP) @[ IoU=0.75      | area=   all | maxDets=100 ] = 0.454
     Average Precision  (AP) @[ IoU=0.50:0.95 | area= small | maxDets=100 ] = 0.240
     Average Precision  (AP) @[ IoU=0.50:0.95 | area=medium | maxDets=100 ] = 0.465
     Average Precision  (AP) @[ IoU=0.50:0.95 | area= large | maxDets=100 ] = 0.590
     Average Recall     (AR) @[ IoU=0.50:0.95 | area=   all | maxDets=  1 ] = 0.344
     Average Recall     (AR) @[ IoU=0.50:0.95 | area=   all | maxDets= 10 ] = 0.545
     Average Recall     (AR) @[ IoU=0.50:0.95 | area=   all | maxDets=100 ] = 0.579
     Average Recall     (AR) @[ IoU=0.50:0.95 | area= small | maxDets=100 ] = 0.370
     Average Recall     (AR) @[ IoU=0.50:0.95 | area=medium | maxDets=100 ] = 0.631
     Average Recall     (AR) @[ IoU=0.50:0.95 | area= large | maxDets=100 ] = 0.751
    ```
- SpineNet-49S
    ```
     Average Precision  (AP) @[ IoU=0.50:0.95 | area=   all | maxDets=100 ] = 0.391
     Average Precision  (AP) @[ IoU=0.50      | area=   all | maxDets=100 ] = 0.587
     Average Precision  (AP) @[ IoU=0.75      | area=   all | maxDets=100 ] = 0.422
     Average Precision  (AP) @[ IoU=0.50:0.95 | area= small | maxDets=100 ] = 0.202
     Average Precision  (AP) @[ IoU=0.50:0.95 | area=medium | maxDets=100 ] = 0.425
     Average Precision  (AP) @[ IoU=0.50:0.95 | area= large | maxDets=100 ] = 0.563
     Average Recall     (AR) @[ IoU=0.50:0.95 | area=   all | maxDets=  1 ] = 0.323
     Average Recall     (AR) @[ IoU=0.50:0.95 | area=   all | maxDets= 10 ] = 0.514
     Average Recall     (AR) @[ IoU=0.50:0.95 | area=   all | maxDets=100 ] = 0.546
     Average Recall     (AR) @[ IoU=0.50:0.95 | area= small | maxDets=100 ] = 0.327
     Average Recall     (AR) @[ IoU=0.50:0.95 | area=medium | maxDets=100 ] = 0.596
     Average Recall     (AR) @[ IoU=0.50:0.95 | area= large | maxDets=100 ] = 0.724
    ```




