# YOLOv7 Object Detection Algorithm on Custom Dataset

## Description

* This repository contains the training code for the [plant disease web page](https://github.com/a-jimenezc/plant-disease-app/tree/master).
* Modified yaml files and custom data set was added to the original [yolo v7 implementation](https://github.com/WongKinYiu/yolov7) implementation.

## Files added

* Added *custom_data.yaml* in *data* folder. This file contains the location of the data for the plant desease app training. Also, it states the number of classes.
* Added *yolo7_plantdoc-tiny.yaml* file to *cfg/training* directory. It contains the architectural description of the model. In this case, the tiny version is used.
* Added *yolov7-tiny.pt* weights, and used *data/hyp.scratch.tiny.yaml* for hyperparametes

## Run

* cd to **yolov7** folder
* Train: python train.py --epochs 200 --workers 1 --device 0 --batch-size 16 --data data/custom_data.yaml --img 416 416 --cfg cfg/training/yolov7_plantdoc-tiny.yaml --weights 'yolov7-tiny.pt' --name yolov7_tiny_plantdoc --hyp data/hyp.scratch.tiny.yaml
* Inference: python detect.py --weights best.pt --conf 0.1 --img-size 416 --source 1.jpg --view-img --no-trace
* Export to onnx format: python export.py --weights best_200epocs.pt --grid --end2end --simplify --topk-all 100 --iou-thres 0.65 --conf-thres 0.35 --img-size 416 416 --max-wh 416



## Resources

- [yolo v7 implementation](https://github.com/WongKinYiu/yolov7) by WongKinYiu
- Dataset: [Plantdoc](https://public.roboflow.com/object-detection/plantdoc)

## Licence

GNU General Public License v3.0

## Author

Antonio Jimenez Caballero

## Contact

[Linkedin](https://www.linkedin.com/in/antonio-jimnzc/)

