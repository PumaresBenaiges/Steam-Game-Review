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

### Preprocessat
Per poder utilitzar l'atribut que és un comentari l'haurem de passar matriu on cada columna serà una paraula.
He creat un nou atribut que és la concatenació del nom del videojoc, l'any de valoració i el comentari. Així al fer l'entrenamnet també es tindran en compte aquests valors.

### Model
| Model | Hiperparametres | Temps | Score |
| -- | -- | -- | -- |
| SGDClassifier        |   |4.63s |  87.9 % |
| Logistic Regression  |   | 4.77s |  88.4 % |
| Perceptron           |    |4.46s |  85.1 % |
| ComplementNB         |    |4.31s |  83.0 % |
| MultinomialNB        |    |4.45s |  78.8 % |
| Nearest Neighbors    |    |3.9s  |  74.7 % |
| Decision Tree        |    |6.05s |  70.9 % |
| Random Forest        |    |4.47s |  57.0 % |
| Bagging              |    |4.94s |  59.3 % |
| AdaBoost             |    |8.34s |  72.7 % |


## Conclusions
El millor model que s'ha aconseguit ha estat la regressió logística i i el SGDC classificador, els dos amb resultats molt similars, he obtingut un accuracy al voltant de 87%-88%.
Al afegir l'any i el nom del videojoc, no ha sigut una millora molt notable, el resultat només ha millorat en algunes decimes.
Al principi per estalviar temps he entrenat els models sense fer servir totes les paraules, agafant només les que sortien més d'un cert nombre de vegades. Com més paraules s'agafen millor accuracy, com que tampoc era tan lent les he agafat totes.
Al no posar el paràmetre stopwords també s'obtenia millor accuracy, així que vol dir que aquestes paraules també eren importants per la predicció.

## Idees per treballar en un futur
