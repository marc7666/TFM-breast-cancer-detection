# Experiments' results Master's thesis

## Transfer learning

### <ins>Experiment 1 - 15/11/2026 - ResNet50</ins>

#### <em>Dataset</em>

- Source: Kaggle dataset

- Link: <ins>[Breast Cancer](https://www.kaggle.com/datasets/ahmedmohamedabdallah/breastcancer)</ins>

- 820 JPG images. Balanced classes: 410 "Cancer", 410 "Negative".

- Split with function:
```python
from sklearn.model_selection import train_test_split

train_test_split()
```

- Preprocessing:
    - Resize to 224x224
    - Color Mode: 'rgb' $\rightarrow$ 3 channels (ResNet50 requires rgb mode)

#### <em>Architecture</em>

| Block | Layers |
| --- | --- |
| Input | `Input(shape=(224, 224, 3))` |
| Base model | `ResNet50(weights='imagenet', include_top=False, input_shape=((224, 224, 3))` |
| Aditional layers | `GlobalAveragePooling2D` $\rightarrow$ `Dense(1024, relu)` $\rightarrow$ `Dropout(0.5)` $\rightarrow$ `Dense(2, softmax)` |

- Total parameters: 25.687.938
- Trainable parameters: 2.100.226
- Non-trainable parameters: 23.587.712

#### <em>Training</em>

- Optimizer: Adam with learning rate 1e-3.
- Loss: sparse categorical cross-entropy
- Metric: accuracy
- Max training epochs: 1000
- Callbacks: `EarlyStopping(monitor="val_loss", patience=20, restore_best_weights=True)`, `ModelCheckpoint("checkpoints/best_resnet.keras", monitor="val_loss", save_best_only=True)` and `ReduceLROnPlateau(monitor="val_loss",patience=20, verbose=1)`
- Hardware: Kaggle environment with 2 x GPU Tesla T4

#### <em>Results</em>

- Test accuracy: 97.56%
- Early stopping at epoch 22 of 1000
- Accuracy/Loss curves for training and validation data

#### <em>ONNX model</em>

- ONNX model saved at `models\Failed experiments\Exp1-15-11-2026-ResNet50.onnx`

#### <em>Additional notes</em>

- Overfitting
