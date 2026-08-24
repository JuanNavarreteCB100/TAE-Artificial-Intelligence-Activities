# TAE Inteligencia Artificial — Módulo 4: Deep Learning
## Repositorio de actividades del Módulo 4 del curso TAE Inteligencia Artificial, enfocado en los fundamentos matemáticos y computacionales del Deep Learning.
## **Docente:** Dr. Germán Pinedo-Díaz  
## **Institución:** CINVESTAV

En las siguientes actividades se reviso: Los fundamentos de las redes neuronales convolucionales (CNN): desde la operación de convolución 1D escrita a mano, pasando por su aplicación en una red convolucional real para clasificación (MNIST-1D), hasta la convolución 2D usada en visión por computadora.

**6_1_1_D Convolución:** Implementación manual (sin librerías) de la convolución 1D con relleno de ceros, variando tamaño de kernel, paso (stride) y dilatación (conv_3_1_1_zp, conv_3_2_1_zp, conv_5_1_1_zp, conv_3_1_2_zp); interpretación de la convolución como suavizado y como aproximación de la derivada; representación de la convolución como multiplicación matricial (get_conv_mat_3_1_1_zp); análisis de la composición de convoluciones (dos convoluciones de kernel 3 equivalen a una de kernel 5).

**6_2_Convolución para MNIST-1D:** Construcción y entrenamiento de una red neuronal convolucional en PyTorch (nn.Conv1d) para clasificar la versión unidimensional de MNIST; arquitectura de tres capas convolucionales (kernel 3, paso 2, sin padding) con activación ReLU, seguidas de aplanamiento y una capa lineal final; entrenamiento con SGD, momentum y scheduler de tasa de aprendizaje; seguimiento de la pérdida y el error de clasificación en entrenamiento y validación por época.

**6_3_2D_Convolución 2D:** Implementación manual de la convolución 2D en NumPy (conv_numpy_1 a conv_numpy_4), progresando desde un solo canal hasta soporte completo de lote, múltiples canales de entrada/salida, stride y padding; validación contra torch.nn.functional.conv2d mediante Error Absoluto Medio; comparación de rendimiento CPU vs. GPU (CUDA/MPS) para convoluciones a gran escala.

---

## Tecnologías
 * Python 3
 * NumPy
 * Matplotlib
 * Jupyter Notebook

## Autor
**Dr. Juan Navarrete Guzmán**  
TAE Inteligencia Artificial — Módulo 4: Deep Learning  
CINVESTAV
