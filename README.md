# Master's thesis

## Project structure

```text
TFM-breast-cancer-detection/
├── src/
│	├── Exp1-01-11-2026 - with inference process.ipynb
│   ├── Exp1-01-11-2026.ipynb
│	├── Exp2-03-11-2026.ipynb 
│	├── Exp3-03-11-2026.ipynb
│	├── Exp4-04-11-2026.ipynb
│	├── Exp5-04-11-2026.ipynb
│	├── Exp6-04-11-2026.ipynb
│	├── Exp7-04-11-2026.ipynb
│	├── Exp8-04-11-2026.ipynb
│	├── Exp9-15-11-2026.ipynb
│   └── README_EXPERIMENTS.md
├── models/
│	├── Failed experiments/
│   	└── Exp9-15-11-2026-CNN.onnx
│	└── Sucessful experiments/
│   	├── Exp1-01-11-2026-CNN.onnx
│   	├── Exp2-03-11-2026-CNN.onnx
│   	├── Exp3-03-11-2026-CNN.onnx
│   	├── Exp4-04-11-2026-CNN.onnx
│   	├── Exp5-04-11-2026-CNN.onnx
│   	├── Exp6-04-11-2026-CNN.onnx
│   	├── Exp7-04-11-2026-CNN.onnx
│   	└── Exp8-04-11-2026-CNN.onnx
├── .gitattributes
├── .gitignore
├── LICENSE.md
└── README.md
```

## Summary table

| Model name               | Deep Learning technique | Accuracy test | Success/Fail status | Reason failure |
| ------------------------ | ----------------------- | ------------- | ------------------- | -------------- |
| Exp1-01-11-2026-CNN.onnx | CNN                     | 92.68%        | Success             | DNA            |
| Exp2-03-11-2026-CNN.onnx | CNN                     | 91.46%        | Success             | DNA            |
| Exp3-03-11-2026-CNN.onnx | CNN                     | 91.46%        | Success             | DNA            |
| Exp4-04-11-2026-CNN.onnx | CNN                     | 95.12%        | Success             | DNA            |
| Exp5-04-11-2026-CNN.onnx | CNN                     | 98.78%        | Success             | DNA            |
| Exp6-04-11-2026-CNN.onnx | CNN                     | 92.68%        | Success             | DNA            |
| Exp7-04-11-2026-CNN.onnx | CNN                     | 96.34%        | Success             | DNA            |
| Exp8-04-11-2026-CNN.onnx | CNN                     | 95.12%        | Success             | DNA            |
| Exp9-15-11-2026-CNN.onnx | CNN                     | 96.34%        | Failure             | Overfitting    |



## Citation

```bibtex
@software{cervera2026tfmUOC,
author		= {Cervera Rosell, Marc},
title		= {{Clasificació de tumors de mama mitjançant imatges}},
year		= {2026},
url			= {https://github.com/marc7666/TFM-breast-cancer-detection},
abstract	= {Source code, models, and experiments developed as part of a Master's Thesis (TFM), focused on applying artificial intelligence techniques for breast cancer detection.}
}
```

## License:

All the files in this repository are licensed under : [CC BY-NC 3.0 ES](https://creativecommons.org/licenses/by-nc/3.0/es/)
