# Parkinson-Mobilenet-Comparison
Spiral and Wave image-based Parkinson's detection experiment using a lightweight deep learning model. Comparing MobileNetV2, custom MobileNetV2, and MobileNetV3-Small to evaluate accuracy, computational efficiency, and potential implementation on mobile/edge devices.

Models Compared
- MobileNetV2 (Normal + Activation Customization)
ReLU + ReLU: All layers (pretrained & fully connected) use ReLU
Hard Swish: All layers use Hard Swish
Hard + ReLU: Pretrained uses Hard Swish, fully connected uses ReLU
- MobileNetV2 (Custom α=0.35)
To reduce the number of neurons and model complexity, the parameter alpha=0.35 is used. Activation variations:
ReLU + ReLU
Hard Swish
Hard + ReLU
- MobileNetV3-Small
Uses the default architecture without modification.

DataSet : 
- HandPD (Kaggle, Clayton Pereira) – 54 spiral images were used for each class.
- Mendeley (Shiva Medasani) – used entirely to increase data variation.
- Parkinson-SpiralDrawing (GitHub, seensiravit) – 60 images were taken per class (54 training, 4 testing, 2 custom).
- Parkinson’s Disease Augmented Hand Drawings (B. Anil Kumar, Mendeley) – all spiral and wave images were used, then separated based on type.
  
After combining and processing, the total data used is:
1,964 Spiral images (Parkinson's & Healthy)
1,632 Wave images (Parkinson's & Healthy)
Link Dataset Final : https://drive.google.com/drive/folders/1RR3sKIvLAUYNjPkfyMbqp6aBkhNOdQmH?usp=sharing 

Environment Setup : 
```bash
  pip install -r requirements.txt
```

Experimental Results
Spiral Detection : 
| Model                            | Precision | Recall | F1-Score | Accuracy |
| -------------------------------- | --------- | ------ | -------- | -------- |
| MobileNetV2 (ReLU + ReLU)        | 0.95      | 0.95   | 0.95     | 0.95     |
| MobileNetV2 (Hard Swish)         | 0.93      | 0.93   | 0.93     | 0.93     |
| MobileNetV2 (Hard + ReLU)        | 0.945     | 0.945  | 0.95     | 0.95     |
| MobileNetV2 Custom (ReLU + ReLU) | 0.93      | 0.935  | 0.93     | 0.93     |
| MobileNetV2 Custom (Hard Swish)  | 0.93      | 0.935  | 0.93     | 0.93     |
| MobileNetV2 Custom (Hard + ReLU) | 0.94      | 0.94   | 0.94     | 0.94     |
| MobileNetV3-Small                | 0.925     | 0.93   | 0.925    | 0.93     |

Wave Detection : 
| Model                            | Precision | Recall | F1-Score | Accuracy |
| -------------------------------- | --------- | ------ | -------- | -------- |
| MobileNetV2 (ReLU + ReLU)        | 0.94      | 0.94   | 0.935    | 0.94     |
| MobileNetV2 (Hard Swish)         | 0.915     | 0.905  | 0.905    | 0.91     |
| MobileNetV2 (Hard + ReLU)        | 0.92      | 0.915  | 0.915    | 0.91     |
| MobileNetV2 Custom (ReLU + ReLU) | 0.92      | 0.91   | 0.91     | 0.91     |
| MobileNetV2 Custom (Hard Swish)  | 0.90      | 0.89   | 0.89     | 0.89     |
| MobileNetV2 Custom (Hard + ReLU) | 0.915     | 0.915  | 0.91     | 0.91     |
| MobileNetV3-Small                | 0.93      | 0.925  | 0.925    | 0.93     |

License
This project is licensed under the MIT License –
