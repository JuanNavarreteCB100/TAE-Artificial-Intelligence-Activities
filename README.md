## Notebook 3.1 — Optimización I: Descenso por Gradiente
## Modulo 4: Deep Learning
# Docente: Dr. German Pinedo-Diaz

## Modelo
$$
y(x) = \sin(z)\exp(-z^2/8), \qquad z = \phi_0 + 0.06\,\phi_1\, x
$$

**Parámetros verdaderos:** $\phi_0 = 3.0$, $\phi_1 = 15.0$

**Actualización de parámetros:**

$$
\phi_{t+1} = \phi_t - \alpha \nabla_\phi L(\phi_t)
$$

---

## Experimentos
### Experimento 1 — Caso base

```python
phi = np.array([-2.0, 5.0])
lr = 8.0
n_steps = 120
```

| Pérdida inicial | Pérdida final |
|---|---|
| 0.14262 | 0.14262 |

**Observación:** El punto de inicio queda lejos del mínimo global. Con 120 pasos y α=8, el modelo apenas empieza a desplazarse. La curva naranja no se ajusta bien a los datos — el descenso es visible en el contorno pero insuficiente para converger.

---

### Experimento 2 — Tasa de aprendizaje muy pequeña (α = 0.5)

```python
phi = np.array([-2.0, 5.0])
lr = 0.5
n_steps = 120
```

| Pérdida inicial | Pérdida final |
|---|---|
| 0.14262 | 0.14173 |

**Observación:** La pérdida apenas disminuyó. El punto naranja prácticamente no se movió del punto inicial en el contorno. Con α tan pequeño, los pasos son demasiado cortos — se necesitarían miles de iteraciones para alcanzar el mínimo. Convergencia **extremadamente lenta**.

---

### Experimento 3 — Tasa de aprendizaje muy grande (α = 15)

```python
phi = np.array([-2.0, 5.0])
lr = 15.0
n_steps = 150
```

| Pérdida inicial | Pérdida final |
|---|---|
| 0.14262 | 0.14884 |

**Observación:** La pérdida **aumentó** respecto al punto de inicio. El gradiente da pasos demasiado grandes y el algoritmo salta por encima del mínimo, moviéndose en dirección incorrecta. Comportamiento de **divergencia**.

---

### Experimento 4 — Tasa de aprendizaje negativa (α = −0.5)

```python
phi = np.array([-2.0, 5.0])
lr = -0.5
n_steps = 120
```

| Pérdida inicial | Pérdida final |
|---|---|
| 0.14262 | 0.14748 |

**Observación:** Al usar α negativo, la actualización se convierte en un **ascenso por gradiente** — el algoritmo se aleja del mínimo en lugar de acercarse. La pérdida sube consistentemente. Esto ilustra por qué el signo de la tasa de aprendizaje es crítico.

---

### Experimento 5 — Mínimo local (α = 5, punto inicial alejado)

```python
phi = np.array([0.0, 10.0])
lr = 5.0
n_steps = 800
```

| Pérdida inicial | Pérdida final |
|---|---|
| 0.14262 | 0.12908 |

**Observación:** La pérdida disminuye pero el algoritmo queda **atrapado en un mínimo local**. Aunque se ejecutaron 800 pasos, el punto no logra alcanzar el mínimo global en φ₀=3, φ₁=15. Esto demuestra que el descenso por gradiente es sensible al punto de inicio — desde ciertas regiones del espacio de parámetros, el gradiente dirige hacia soluciones subóptimas.

---

### Experimento 6 — Convergencia exitosa 

```python
phi = np.array([1.0, 12.0])
lr = 3.0
n_steps = 500
```

| Pérdida inicial | Pérdida final | φ₀ final | φ₁ final |
|---|---|---|---|
| 0.14262 | **0.00721** | 2.745 | 13.569 |

**Observación:** Arrancando más cerca del mínimo global y con una tasa moderada, el algoritmo **converge exitosamente**. La curva naranja se superpone casi perfectamente con la curva verdadera (roja punteada). Los parámetros finales φ₀=2.745 y φ₁=13.569 son muy cercanos a los valores verdaderos φ₀=3 y φ₁=15. La trayectoria en el contorno muestra un descenso suave hacia la región de mínima pérdida.

---

## Conclusiones

| Factor | Efecto observado |
|---|---|
| α demasiado pequeño (0.5) | Convergencia extremadamente lenta, casi sin movimiento |
| α adecuado (3.0–8.0) | Descenso progresivo, converge con suficientes pasos |
| α demasiado grande (15.0) | Divergencia — la pérdida aumenta |
| α negativo (−0.5) | Ascenso por gradiente — se aleja del mínimo |
| Punto inicial lejano | Riesgo de quedar atrapado en mínimo local |
| Punto inicial cercano al mínimo | Convergencia exitosa con menos iteraciones |

El descenso por gradiente es sensible tanto a la **tasa de aprendizaje** como al **punto de inicio**. Una α adecuada permite pasos suficientemente grandes para avanzar, pero sin sobrepasar el mínimo. La elección del punto inicial determina hacia qué mínimo converge el algoritmo en superficies de pérdida no convexas como la del modelo Gabor.

## Autor
Dr. Juan Navarrete Guzman
TAE Inteligencia Artificial — Modulo 4: Deep Learning
CINVESTAV
