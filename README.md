# Math Warm-Up — TAE Inteligencia Artificial
## Modulo 4: Deep Learning
# Docente: Dr. German Pinedo-Diaz

## Actividad 1.1 — Math Warm-Up
Esta actividad se estableció los fundamentos matemáticos. 
El punto de partida fue entender la diferencia entre una función lineal pura y una función afín: aunque f(x)=β+ωxf(x) = \beta + \omega x f(x)=β+ωx dibuja una línea recta, el intercepto β\beta β rompe la propiedad de aditividad estricta. Es la razón por la que en redes neuronales se habla técnicamente de "capas afines" aunque en la práctica se les llame lineales.

La extensión a múltiples dimensiones (hiperplanos, formulación matricial Y=β+XΩ⊤Y = \beta + X\Omega^\top Y=β+XΩ⊤) dejó claro que el paso a problemas más complejos no cambia la idea de fondo: seguimos aplicando una transformación plana. Lo que sí cambia es la escala, esta es la importancia de las operaciones matriciales eficientes para GPU.

La reflexión más importante es por qué se necesitan no linealidades: apilar capas lineales sigue produciendo algo lineal. Las funciones de activación (ReLU, sigmoid, tanh) son las que introducen las "curvas" necesarias para que una red pueda aprender patrones complejos. Sin ellas, una red profunda sería equivalente a una sola capa.

## Actividad 1.2 — Regresión Lineal
Esta actividad se implemento el modelo y^=ϕ0+ϕ1x\hat{y} = \phi_0 + \phi_1 x y^=ϕ0+ϕ1x y la función de pérdida cuadrática permitió ver de primera mano cómo pequeños cambios en los parámetros afectan qué tan bien el modelo describe los datos.

El ejercicio de ajuste manual mediante descenso coordinado fijar un parámetro, optimizar el otro : es una versión simplificada del gradiente descendente, y experimentarlo manualmente construye una intuición que ninguna fórmula por sí sola puede dar. La visualización de la superficie de pérdida como mapa de calor confirmó visualmente que el proceso de optimización es literalmente "bajar una colina" en el espacio de parámetros.

En conjunto, ambas actividades forman un puente sólido entre el álgebra lineal y el aprendizaje automático práctico.


## Autor
Dr. Juan Navarrete Guzman
TAE Inteligencia Artificial — Modulo 4: Deep Learning
CINVESTAV
