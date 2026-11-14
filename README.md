# TD VI — Trabajo Práctico N°3

Este repositorio contiene todo el código fuente correspondiente al *Trabajo Práctico N°3* de la materia de *TD VI: Inteligencia Artificial*. El dataset usado es la versión RGB de **EuroSAT**.

El trabajo aborda la clasificación de estas imágenes mediante redes neuronales convolucionales. Se entrena desde cero una arquitectura propia y se la compara contra un esquema de *transfer learning* sobre ResNet18 preentrenada en ImageNet.

## Estructura del repositorio

```text
.
├── data/
│   └── eurosat/                       # Dataset EuroSAT, descargado mediante torchvision
├── informe/                           # Informe sobre el análisis y la toma de decisiones
├── .gitignore
├── README.md
├── arquitectura_custom.ipynb          # Jupyter Notebook (TP)
├── consigna.pdf
├── modelo_custom.pt                   # Pesos de la CNN entrenada desde cero
├── modelo_resnet.pt                   # Pesos de ResNet18 ajustada por transfer learning
└── requirements.txt                   # Dependencias del proyecto
```

## Replicabilidad del entorno

El proyecto utiliza **Python** y Jupyter Notebooks.

Para instalar las dependencias utilizando un entorno virtual:

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

La celda de carga de datos descarga EuroSAT automáticamente mediante `torchvision.datasets.EuroSAT` sobre el directorio `data/`, por lo que no es necesario obtener el dataset por separado.

Para reproducir el entrenamiento se recomienda contar con GPU. Los pesos entrenados se incluyen en el repositorio (`modelo_custom.pt` y `modelo_resnet.pt`), por lo que las secciones de evaluación pueden ejecutarse sin reentrenar los modelos.