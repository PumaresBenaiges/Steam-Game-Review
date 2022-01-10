# Pràctica Kaggle APC UAB 2021-22
### Nom: Júlia Pumares Benaiges
### DATASET: Steam Game Review Dataset
### URL: [kaggle](https://www.kaggle.com/arashnic/game-review-dataset)

## Resum
El dataset utilitza dades de valoracions de videojocs fetes per usuaris
Tenim 17494 dades d'entrenament i 8045 dades de test. Tenim 4 atributs:
 - El nom del videojoc
 - L'any de la valoració
 - El comentari que van fer per valorar el videojoc 
 - Un boolea que diu si l'usuari recomana el videojoc(1) o sino el recomana(0)

### Objectius del dataset
Volem predir si l'usuari recomanarà el videojoc o no basant-nos en el comentari de valoració que ha fet i en altres atributs.

## Experiments


### Preprocessat

### Model
| Model | Hiperparametres | Mètrica | Temps |
| -- | -- | -- | -- |
| SGDClassifier        | 4.63s |  87.9 % |
| Logistic Regression  | 4.77s |  88.4 % |
| Perceptron           | 4.46s |  85.1 % |
| ComplementNB         | 4.31s |  83.0 % |
| MultinomialNB        | 4.45s |  78.8 % |
| Nearest Neighbors    | 3.9s  |  74.7 % |
| Decision Tree        | 6.05s |  70.9 % |
| Random Forest        | 4.47s |  57.0 % |
| Bagging              | 4.94s |  59.3 % |
| AdaBoost             | 8.34s |  72.7 % |

## Demo
Per tal de fer una prova, es pot fer servir amb la següent comanda
``` python3 demo/demo.py --input here ```
## Conclusions
El millor model que s'ha aconseguit ha estat

## Idees per treballar en un futur
