# Resumen de la prueba con fecha 12/06/2023 16:50:28

Tiempo de entrenamiento del modelo: 01 horas 55 minutos 29 segundos
.
## Arquitectura del modelo.

```
Model: "model"

__________________________________________________________________________________________________

 Layer (type)                   Output Shape         Param #     Connected to                     

==================================================================================================

 images (InputLayer)            [(None, 512, 512, 1  0           []                               

                                )]                                                                

                                                                                                  

 Conv2d_2_1_16 (Conv2D)         (None, 128, 128, 16  32          ['images[0][0]']                 

                                )                                                                 

                                                                                                  

 Conv2d_1_1_16 (Conv2D)         (None, 510, 510, 16  160         ['images[0][0]']                 

                                )                                                                 

                                                                                                  

 Up2d_2_2_16 (UpSampling2D)     (None, 512, 512, 16  0           ['Conv2d_2_1_16[0][0]']          

                                )                                                                 

                                                                                                  

 Conv2d_1_2_16 (Conv2D)         (None, 508, 508, 16  2320        ['Conv2d_1_1_16[0][0]']          

                                )                                                                 

                                                                                                  

 Crop2d_2_3_16 (Cropping2D)     (None, 508, 508, 16  0           ['Up2d_2_2_16[0][0]']            

                                )                                                                 

                                                                                                  

 Conc_1_16 (Concatenate)        (None, 508, 508, 32  0           ['Conv2d_1_2_16[0][0]',          

                                )                                 'Crop2d_2_3_16[0][0]']          

                                                                                                  

 max_pooling2d (MaxPooling2D)   (None, 254, 254, 32  0           ['Conc_1_16[0][0]']              

                                )                                                                 

                                                                                                  

 Conv2d_2_1_32 (Conv2D)         (None, 64, 64, 32)   1056        ['max_pooling2d[0][0]']          

                                                                                                  

 Conv2d_1_1_32 (Conv2D)         (None, 252, 252, 32  9248        ['max_pooling2d[0][0]']          

                                )                                                                 

                                                                                                  

 Up2d_2_2_32 (UpSampling2D)     (None, 256, 256, 32  0           ['Conv2d_2_1_32[0][0]']          

                                )                                                                 

                                                                                                  

 Conv2d_1_2_32 (Conv2D)         (None, 250, 250, 32  9248        ['Conv2d_1_1_32[0][0]']          

                                )                                                                 

                                                                                                  

 Crop2d_2_3_32 (Cropping2D)     (None, 250, 250, 32  0           ['Up2d_2_2_32[0][0]']            

                                )                                                                 

                                                                                                  

 Conc_1_32 (Concatenate)        (None, 250, 250, 64  0           ['Conv2d_1_2_32[0][0]',          

                                )                                 'Crop2d_2_3_32[0][0]']          

                                                                                                  

 max_pooling2d_1 (MaxPooling2D)  (None, 125, 125, 64  0          ['Conc_1_32[0][0]']              

                                )                                                                 

                                                                                                  

 Conv2d_2_1_64 (Conv2D)         (None, 32, 32, 64)   4160        ['max_pooling2d_1[0][0]']        

                                                                                                  

 Conv2d_1_1_64 (Conv2D)         (None, 123, 123, 64  36928       ['max_pooling2d_1[0][0]']        

                                )                                                                 

                                                                                                  

 Up2d_2_2_64 (UpSampling2D)     (None, 128, 128, 64  0           ['Conv2d_2_1_64[0][0]']          

                                )                                                                 

                                                                                                  

 Conv2d_1_2_64 (Conv2D)         (None, 121, 121, 64  36928       ['Conv2d_1_1_64[0][0]']          

                                )                                                                 

                                                                                                  

 Crop2d_2_3_64 (Cropping2D)     (None, 121, 121, 64  0           ['Up2d_2_2_64[0][0]']            

                                )                                                                 

                                                                                                  

 Conc_1_64 (Concatenate)        (None, 121, 121, 12  0           ['Conv2d_1_2_64[0][0]',          

                                8)                                'Crop2d_2_3_64[0][0]']          

                                                                                                  

 additional_info (InputLayer)   [(None, 3)]          0           []                               

                                                                                                  

 max_pooling2d_2 (MaxPooling2D)  (None, 60, 60, 128)  0          ['Conc_1_64[0][0]']              

                                                                                                  

 additional_info_dense_1 (Dense  (None, 64)          256         ['additional_info[0][0]']        

 )                                                                                                

                                                                                                  

 flatten (Flatten)              (None, 460800)       0           ['max_pooling2d_2[0][0]']        

                                                                                                  

 additional_info_dense_2 (Dense  (None, 32)          2080        ['additional_info_dense_1[0][0]']

 )                                                                                                

                                                                                                  

 concatenate (Concatenate)      (None, 460832)       0           ['flatten[0][0]',                

                                                                  'additional_info_dense_2[0][0]']

                                                                                                  

 dense_1 (Dense)                (None, 128)          58986624    ['concatenate[0][0]']            

                                                                                                  

 dense_2 (Dense)                (None, 64)           8256        ['dense_1[0][0]']                

                                                                                                  

 outputs (Dense)                (None, 14)           910         ['dense_2[0][0]']                

                                                                                                  

==================================================================================================

Total params: 59,098,206

Trainable params: 59,098,206

Non-trainable params: 0

__________________________________________________________________________________________________

```

![Arquitectura de la red](images/model-2023-06-12.16-50-28.png)

## Pérdida y precisión binaria.

![Pérdida y precisión binaria](images/loss-binary-accuracy-2023-06-12.16-50-28.png)

## Matriz de confusión.

* Atelectasis
```python
[[854  55]
 [ 81  10]]
```

* Cardiomegaly
```python
[[951   5]
 [ 41   3]]
```

* Consolidation
```python
[[951  12]
 [ 37   0]]
```

* Edema
```python
[[974   0]
 [ 26   0]]
```

* Effusion
```python
[[840  63]
 [ 80  17]]
```

* Emphysema
```python
[[961   4]
 [ 34   1]]
```

* Fibrosis
```python
[[960  13]
 [ 25   2]]
```

* Hernia
```python
[[996   0]
 [  4   0]]
```

* Infiltration
```python
[[761  79]
 [142  18]]
```

* Mass
```python
[[951  21]
 [ 28   0]]
```

* Nodule
```python
[[953  12]
 [ 35   0]]
```

* Pleural_Thickening
```python
[[951  19]
 [ 30   0]]
```

* Pneumonia
```python
[[983   3]
 [ 14   0]]
```

* Pneumothorax
```python
[[941  20]
 [ 35   4]]
```

## Resultados de la clasificación.

```
                    precision    recall  f1-score   support

       Atelectasis       0.15      0.11      0.13        91
      Cardiomegaly       0.38      0.07      0.12        44
     Consolidation       0.00      0.00      0.00        37
             Edema       0.00      0.00      0.00        26
          Effusion       0.21      0.18      0.19        97
         Emphysema       0.20      0.03      0.05        35
          Fibrosis       0.13      0.07      0.10        27
            Hernia       0.00      0.00      0.00         4
      Infiltration       0.19      0.11      0.14       160
              Mass       0.00      0.00      0.00        28
            Nodule       0.00      0.00      0.00        35
Pleural_Thickening       0.00      0.00      0.00        30
         Pneumonia       0.00      0.00      0.00        14
      Pneumothorax       0.17      0.10      0.13        39

         micro avg       0.15      0.08      0.11       667
         macro avg       0.10      0.05      0.06       667
      weighted avg       0.15      0.08      0.10       667
       samples avg       0.04      0.03      0.03       667

```

## Curvas ROC de cada etiqueta.

![Curvas ROC de cada etiqueta](images/ROC-curves-2023-06-12.16-50-28.png)

## Ejemplos de las predicciones del modelo.


    Verde: Clasificación correcta

    Amarillo: Clasificación parcial

    Rojo: Clasificación incorrecta

![Tests](images/tests-2023-06-12.16-50-28.png)

