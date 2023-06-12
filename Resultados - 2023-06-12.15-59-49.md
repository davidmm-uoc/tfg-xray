# Resumen de la prueba con fecha 12/06/2023 15:59:49

Tiempo de entrenamiento del modelo: 00 horas 34 minutos 29 segundos
.
## Arquitectura del modelo.

```
Model: "sequential"

_________________________________________________________________

 Layer (type)                Output Shape              Param #   

=================================================================

 conv2d (Conv2D)             (None, 510, 510, 32)      320       

                                                                 

 max_pooling2d (MaxPooling2D  (None, 255, 255, 32)     0         

 )                                                               

                                                                 

 flatten (Flatten)           (None, 2080800)           0         

                                                                 

 dense (Dense)               (None, 128)               266342528 

                                                                 

 dense_1 (Dense)             (None, 14)                1806      

                                                                 

=================================================================

Total params: 266,344,654

Trainable params: 266,344,654

Non-trainable params: 0

_________________________________________________________________

```

![Arquitectura de la red](images/model-2023-06-12.15-59-49.png)

## Pérdida y precisión binaria.

![Pérdida y precisión binaria](images/loss-binary-accuracy-2023-06-12.15-59-49.png)

## Matriz de confusión.

* Atelectasis
```python
[[909   0]
 [ 91   0]]
```

* Cardiomegaly
```python
[[962   0]
 [ 38   0]]
```

* Consolidation
```python
[[961   0]
 [ 39   0]]
```

* Edema
```python
[[986   0]
 [ 14   0]]
```

* Effusion
```python
[[905   0]
 [ 95   0]]
```

* Emphysema
```python
[[977   0]
 [ 23   0]]
```

* Fibrosis
```python
[[966   0]
 [ 34   0]]
```

* Hernia
```python
[[993   0]
 [  7   0]]
```

* Infiltration
```python
[[  0 831]
 [  0 169]]
```

* Mass
```python
[[966   0]
 [ 34   0]]
```

* Nodule
```python
[[952   0]
 [ 48   0]]
```

* Pleural_Thickening
```python
[[956   0]
 [ 44   0]]
```

* Pneumonia
```python
[[989   0]
 [ 11   0]]
```

* Pneumothorax
```python
[[965   0]
 [ 35   0]]
```

## Resultados de la clasificación.

```
                    precision    recall  f1-score   support

       Atelectasis       0.00      0.00      0.00        91
      Cardiomegaly       0.00      0.00      0.00        38
     Consolidation       0.00      0.00      0.00        39
             Edema       0.00      0.00      0.00        14
          Effusion       0.00      0.00      0.00        95
         Emphysema       0.00      0.00      0.00        23
          Fibrosis       0.00      0.00      0.00        34
            Hernia       0.00      0.00      0.00         7
      Infiltration       0.17      1.00      0.29       169
              Mass       0.00      0.00      0.00        34
            Nodule       0.00      0.00      0.00        48
Pleural_Thickening       0.00      0.00      0.00        44
         Pneumonia       0.00      0.00      0.00        11
      Pneumothorax       0.00      0.00      0.00        35

         micro avg       0.17      0.25      0.20       682
         macro avg       0.01      0.07      0.02       682
      weighted avg       0.04      0.25      0.07       682
       samples avg       0.17      0.12      0.13       682

```

## Curvas ROC de cada etiqueta.

![Curvas ROC de cada etiqueta](images/ROC-curves-2023-06-12.15-59-49.png)

## Ejemplos de las predicciones del modelo.


    Verde: Clasificación correcta

    Amarillo: Clasificación parcial

    Rojo: Clasificación incorrecta

![Tests](images/tests-2023-06-12.15-59-49.png)

