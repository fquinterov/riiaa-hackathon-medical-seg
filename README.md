# Data augmentation con modelos generativos para la mejora de segmentación de imágenes médicas para superar la barrera de atención especializada en salud pública en Latinoamérica
Nuestro método propuesto consiste en usar modelos generativos (GAN o modelos de difusión) para generar imágenes sintéticas usando el limitado dataset de entrada de imágenes reales. Con el modelo generativo podremos crear un dataset de imágenes sintéticas grande. Una vez tengamos esto, podremos entrenar una red de segmentación (la cual podría ser una U-Net) en donde solo usemos las imágenes sintéticas. Este modelo puede que no sea el mejor para segmentar imágenes reales. Para resolver este problema proponemos una segunda etapa en la que usemos knowledge distillation para transferir lo aprendido con las imágenes sintéticas en un entrenamiento de la U-Net de segmentación usando solo las imágenes reales. También podríamos solo entrenar la U-Net con las imágenes reales inicializando con los pesos aprendidos en el entrenamiento hecho con las imágenes sintéticas. De esta forma pretendemos mejorar los resultados de segmentación.

![Frame 1 (5)](https://github.com/fquinterov/riiaa-hackathon-medical-seg/assets/60611975/dc607f7a-5964-45df-9421-d0592dd05cad)

### Datasets
Los datos pueden ser descargados en los siguientes enlaces:

- https://www.kaggle.com/datasets/nikhilroxtomar/brain-tumor-segmentation?select=images
- https://www.kaggle.com/datasets/rasoulisaeid/lung-cancer-segment
