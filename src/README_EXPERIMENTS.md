# Experiments' results Master's thesis

## CNNs

### <ins>Experiment 1 - 01/11/2026</ins>

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
    - Color Mode: 'grayscale' $\rightarrow$ 1 channel

#### <em>Architecture</em>

| Block | Layers |
| --- | --- |
| Input | `Input(shape=(224, 224, 1))` |
| Feature extractor | `Conv2D(16, 5x5, relu)` $\rightarrow$ `MaxPool2D` $\rightarrow$ `Conv2D(32, 3x3, relu)` $\rightarrow$ `MaxPool2D` $\rightarrow$ `Conv2D(64, 3x3, relu)` $\rightarrow$ `GlobalAveragePooling2D` |
| Classifier | `Dense(1024, relu)` $\rightarrow$ `Dropout(0.5)` $\rightarrow$ `Dense(2, softmax)` |

- Total parameters: 92.162
- Trainable parameters: 92.162
- Non-trainable parameters: 0

#### <em>Training</em>

- Optimizer: Adam with learning rate 1e-3.
- Loss: sparse categorical cross-entropy
- Metric: accuracy
- Max training epochs: 300
- Callbacks: `EarlyStopping(monitor="val_loss", patience=5, restore_best_weights=True)` and `ModelCheckpoint("checkpoints/best.h5", monitor="val_loss", save_best_only=True)`
- Hardware: Kaggle environment with 2 x GPU Tesla T4

#### <em>Results</em>

- Test accuracy: 92.68%
- Early stopping at epoch 15 of 300
- Accuracy/Loss curves for training and validation data

#### <em>ONNX model</em>

- ONNX model saved at `models\Successful experiments\Exp1-01-11-2026-CNN.onnx`

#### <em>Additional notes</em>

- `.h5` is a legacy Keras format. `.keras` is recommended for future experiments.

### <ins>Experiment 2 - 03/11/2026</ins>

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
    - Color Mode: 'grayscale' $\rightarrow$ 1 channel

#### <em>Architecture</em>

| Block | Layers |
| --- | --- |
| Input | `Input(shape=(224, 224, 1))` |
| Feature extractor | `Conv2D(32, 5x5, relu)` $\rightarrow$ `MaxPool2D` $\rightarrow$ `Conv2D(64, 3x3, relu)` $\rightarrow$ `MaxPool2D` $\rightarrow$ `Conv2D(128, 3x3, relu)` $\rightarrow$ `MaxPool2D` $\rightarrow$ `Conv2D(256, 3x3, relu)` $\rightarrow$ `GlobalAveragePooling2D` |
| Classifier | `Dense(1024, relu)` $\rightarrow$ `Dropout(0.5)` $\rightarrow$ `Dense(2, softmax)` |

- Total parameters: 653.570
- Trainable parameters: 653.570
- Non-trainable parameters: 0

#### <em>Training</em>

- Optimizer: Adam with learning rate 1e-3.
- Loss: sparse categorical cross-entropy
- Metric: accuracy
- Max training epochs: 300
- Callbacks: `EarlyStopping(monitor="val_loss", patience=5, restore_best_weights=True)` and `ModelCheckpoint("checkpoints/best.h5", monitor="val_loss", save_best_only=True)`
- Hardware: Kaggle environment with 2 x GPU Tesla T4

#### <em>Results</em>

- Test accuracy: 91.46%
- Early stopping at epoch 17 of 300
- Accuracy/Loss curves for training and validation data

#### <em>ONNX model</em>

- ONNX model saved at `models\Successful experiments\Exp2-03-11-2026-CNN.onnx`

#### <em>Additional notes</em>

- `.h5` is a legacy Keras format. `.keras` is recommended for future experiments.

### <ins>Experiment 3 - 03/11/2026</ins>

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
    - Color Mode: 'grayscale' $\rightarrow$ 1 channel

#### <em>Architecture</em>

| Block | Layers |
| --- | --- |
| Input | `Input(shape=(224, 224, 1))` |
| Feature extractor | `Conv2D(32, 5x5, relu)` $\rightarrow$ `MaxPool2D` $\rightarrow$ `Conv2D(64, 3x3, relu)` $\rightarrow$ `MaxPool2D` $\rightarrow$ `Conv2D(128, 3x3, relu)` $\rightarrow$ `MaxPool2D` $\rightarrow$ `Conv2D(256, 3x3, relu)` $\rightarrow$ `GlobalAveragePooling2D` |
| Classifier | `Dense(1024, relu)` $\rightarrow$ `Dropout(0.5)` $\rightarrow$ `Dense(2, softmax)` |

- Total parameters: 653.570
- Trainable parameters: 653.570
- Non-trainable parameters: 0

#### <em>Training</em>

- Optimizer: Adam with learning rate 1e-3.
- Loss: sparse categorical cross-entropy
- Metric: accuracy
- Max training epochs: 300
- Callbacks: `EarlyStopping(monitor="val_loss", patience=5, restore_best_weights=True)`, `ModelCheckpoint("checkpoints/best.h5", monitor="val_loss", save_best_only=True)` and `ReduceLROnPlateau(monitor="val_loss",patience=2, verbose=1)`
- Hardware: Kaggle environment with 2 x GPU Tesla T4

#### <em>Results</em>

- Test accuracy: 91.46%
- Early stopping at epoch 12 of 300
- Accuracy/Loss curves for training and validation data

#### <em>ONNX model</em>

- ONNX model saved at `models\Successful experiments\Exp3-03-11-2026-CNN.onnx`

#### <em>Additional notes</em>

- `.h5` is a legacy Keras format. `.keras` is recommended for future experiments.

### <ins>Experiment 4 - 04/11/2026</ins>

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
    - Color Mode: 'grayscale' $\rightarrow$ 1 channel

#### <em>Architecture</em>

| Block | Layers |
| --- | --- |
| Input | `Input(shape=(224, 224, 1))` |
| Feature extractor | `Conv2D(32, 5x5, relu)` $\rightarrow$ `MaxPool2D` $\rightarrow$ `Conv2D(64, 3x3, relu)` $\rightarrow$ `MaxPool2D` $\rightarrow$ `Conv2D(128, 3x3, relu)` $\rightarrow$ `MaxPool2D` $\rightarrow$ `Conv2D(256, 3x3, relu)` $\rightarrow$ `GlobalAveragePooling2D` |
| Classifier | `Dense(1024, relu)` $\rightarrow$ `Dropout(0.3)` $\rightarrow$ `Dense(2, softmax)` |

- Total parameters: 653.570
- Trainable parameters: 653.570
- Non-trainable parameters: 0

#### <em>Training</em>

- Optimizer: Adam with learning rate 1e-3.
- Loss: sparse categorical cross-entropy
- Metric: accuracy
- Max training epochs: 300
- Callbacks: `EarlyStopping(monitor="val_loss", patience=10, restore_best_weights=True)`, `ModelCheckpoint("checkpoints/best.keras", monitor="val_loss", save_best_only=True)` and `ReduceLROnPlateau(monitor="val_loss",patience=2, verbose=1)`
- Hardware: Kaggle environment with 2 x GPU Tesla T4

#### <em>Results</em>

- Test accuracy: 95.12%
- Early stopping at epoch 30 of 300
- Accuracy/Loss curves for training and validation data

#### <em>ONNX model</em>

- ONNX model saved at `models\Successful experiments\Exp4-04-11-2026-CNN.onnx`

#### <em>Additional notes</em>

- First model with Confusion matrix calculation.

### <ins>Experiment 5 - 04/11/2026</ins>

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
    - Color Mode: 'grayscale' $\rightarrow$ 1 channel

#### <em>Architecture</em>

| Block | Layers |
| --- | --- |
| Input | `Input(shape=(224, 224, 1))` |
| Feature extractor | `Conv2D(32, 5x5, relu)` $\rightarrow$ `MaxPool2D` $\rightarrow$ `Conv2D(64, 3x3, relu)` $\rightarrow$ `MaxPool2D` $\rightarrow$ `Conv2D(128, 3x3, relu)` $\rightarrow$ `MaxPool2D` $\rightarrow$ `Conv2D(256, 3x3, relu)` $\rightarrow$ `GlobalAveragePooling2D` |
| Classifier | `Dense(1024, relu)` $\rightarrow$ `Dense(2, softmax)` |

- Total parameters: 653.570
- Trainable parameters: 653.570
- Non-trainable parameters: 0

#### <em>Training</em>

- Optimizer: Adam with learning rate 1e-3.
- Loss: sparse categorical cross-entropy
- Metric: accuracy
- Max training epochs: 1000
- Callbacks: `EarlyStopping(monitor="val_loss", patience=20, restore_best_weights=True)`, `ModelCheckpoint("checkpoints/best.keras", monitor="val_loss", save_best_only=True)` and `ReduceLROnPlateau(monitor="val_loss",patience=20, verbose=1)`
- Hardware: Kaggle environment with 2 x GPU Tesla T4

#### <em>Results</em>

- Test accuracy: 98.78%
- Early stopping at epoch 128 of 1000
- Accuracy/Loss curves for training and validation data

#### <em>ONNX model</em>

- ONNX model saved at `models\Successful experiments\Exp5-04-11-2026-CNN.onnx`

#### <em>Additional notes</em>

### <ins>Experiment 6 - 04/11/2026</ins>

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
    - Color Mode: 'grayscale' $\rightarrow$ 1 channel

#### <em>Architecture</em>

| Block | Layers |
| --- | --- |
| Input | `Input(shape=(224, 224, 1))` |
| Feature extractor | `Conv2D(32, 5x5, relu)` $\rightarrow$ `MaxPool2D` $\rightarrow$ `Conv2D(64, 3x3, relu)` $\rightarrow$ `MaxPool2D` $\rightarrow$ `Conv2D(128, 3x3, relu)` $\rightarrow$ `MaxPool2D` $\rightarrow$ `Conv2D(256, 3x3, relu)` $\rightarrow$ `GlobalAveragePooling2D` |
| Classifier | `Dense(1024, relu)` $\rightarrow$ `Dense(2, softmax)` |

- Total parameters: 653.570
- Trainable parameters: 653.570
- Non-trainable parameters: 0

#### <em>Training</em>

- Optimizer: Adam with learning rate 1e-3.
- Loss: sparse categorical cross-entropy
- Metric: accuracy
- Max training epochs: 1000
- Callbacks: `EarlyStopping(monitor="val_loss", patience=20, restore_best_weights=True)`, `ModelCheckpoint("checkpoints/best.keras", monitor="val_loss", save_best_only=True)` and `ReduceLROnPlateau(monitor="val_loss",patience=20, verbose=1)`
- Hardware: Kaggle environment with 2 x GPU Tesla T4

#### <em>Results</em>

- Test accuracy: 92.68%
- Early stopping at epoch 152 of 1000
- Accuracy/Loss curves for training and validation data

#### <em>ONNX model</em>

- ONNX model saved at `models\Successful experiments\Exp6-04-11-2026-CNN.onnx`

#### <em>Additional notes</em>

### <ins>Experiment 7 - 04/11/2026</ins>

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
    - Color Mode: 'grayscale' $\rightarrow$ 1 channel

#### <em>Architecture</em>

| Block | Layers |
| --- | --- |
| Input | `Input(shape=(224, 224, 1))` |
| Feature extractor | `Conv2D(32, 5x5, relu)` $\rightarrow$ `MaxPool2D` $\rightarrow$ `Conv2D(64, 3x3, relu)` $\rightarrow$ `MaxPool2D` $\rightarrow$ `Conv2D(128, 3x3, relu)` $\rightarrow$ `MaxPool2D` $\rightarrow$ `Conv2D(256, 3x3, relu)` $\rightarrow$ `GlobalAveragePooling2D` |
| Classifier | `Dense(1024, relu)` $\rightarrow$ `Dropout(0.3)` $\rightarrow$  `Dense(2, softmax)` |

- Total parameters: 653.570
- Trainable parameters: 653.570
- Non-trainable parameters: 0

#### <em>Training</em>

- Optimizer: Adam with learning rate 1e-3.
- Loss: sparse categorical cross-entropy
- Metric: accuracy
- Max training epochs: 1000
- Callbacks: `EarlyStopping(monitor="val_loss", patience=20, restore_best_weights=True)`, `ModelCheckpoint("checkpoints/best.keras", monitor="val_loss", save_best_only=True)` and `ReduceLROnPlateau(monitor="val_loss",patience=20, verbose=1)`
- Hardware: Kaggle environment with 2 x GPU Tesla T4

#### <em>Results</em>

- Test accuracy: 96.34%
- Early stopping at epoch 148 of 1000
- Accuracy/Loss curves for training and validation data

#### <em>ONNX model</em>

- ONNX model saved at `models\Successful experiments\Exp7-04-11-2026-CNN.onnx`

#### <em>Additional notes</em>

### <ins>Experiment 8 - 04/11/2026</ins>

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
    - Color Mode: 'grayscale' $\rightarrow$ 1 channel

#### <em>Architecture</em>

| Block | Layers |
| --- | --- |
| Input | `Input(shape=(224, 224, 1))` |
| Feature extractor | `Conv2D(32, 5x5, relu)` $\rightarrow$ `MaxPool2D` $\rightarrow$ `Conv2D(64, 3x3, relu)` $\rightarrow$ `MaxPool2D` $\rightarrow$ `Conv2D(128, 3x3, relu)` $\rightarrow$ `MaxPool2D` $\rightarrow$ `Conv2D(256, 3x3, relu)` $\rightarrow$ `GlobalAveragePooling2D` |
| Classifier | `Dense(1024, relu)` $\rightarrow$ `Dropout(0.5)` $\rightarrow$  `Dense(2, softmax)` |

- Total parameters: 653.570
- Trainable parameters: 653.570
- Non-trainable parameters: 0

#### <em>Training</em>

- Optimizer: Adam with learning rate 1e-3.
- Loss: sparse categorical cross-entropy
- Metric: accuracy
- Max training epochs: 1000
- Callbacks: `EarlyStopping(monitor="val_loss", patience=20, restore_best_weights=True)`, `ModelCheckpoint("checkpoints/best.keras", monitor="val_loss", save_best_only=True)` and `ReduceLROnPlateau(monitor="val_loss",patience=20, verbose=1)`
- Hardware: Kaggle environment with 2 x GPU Tesla T4

#### <em>Results</em>

- Test accuracy: 95.12%
- Early stopping at epoch 128 of 1000
- Accuracy/Loss curves for training and validation data

#### <em>ONNX model</em>

- ONNX model saved at `models\Successful experiments\Exp8-04-11-2026-CNN.onnx`

#### <em>Additional notes</em>