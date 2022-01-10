# Pràctica Kaggle APC UAB 2021-22
### Nom: Júlia Pumares Benaiges
### DATASET: Steam Game Review Dataset
### URL: [kaggle](https://www.kaggle.com/arashnic/game-review-dataset)

## Resum
El dataset utilitza dades de valoracions de videojocs fetes per usuaris.
Hi ha 17494 dades d'entrenament i 8045 dades de test. 

Tenim 4 atributs:
 - Title: El nom del videojoc
 - Year: L'any de la valoració
 - User_review: El comentari que van fer per valorar el videojoc 
 - User_suggestion: Un boolea que diu si l'usuari recomana el videojoc(1) o sino el recomana(0)

### Objectius del dataset
Volem predir si l'usuari recomanarà el videojoc o no basant-nos en el comentari de valoració que ha fet i en altres atributs.

### Preprocessat
Per poder utilitzar l'atribut que és un comentari l'haurem de passar matriu on cada columna serà una paraula.
i per això he creat un nou atribut que és la concatenació del nom del videojoc, l'any de valoració i el comentari. Així al fer l'entrenamnet també es tindran en compte aquests valors.

### Models
| Model | Hiperparametres | Temps | Score |
| -- | -- | -- | -- |
| SGDClassifier        | penalty='l2', alpha=0.0001, max_iter=91, tol=0.01 |1.62s |  87.9 % |
| Logistic Regression  | C=12.0, fit_intercept=True, penalty='l2', tol=0.1 | 1.8s |  88.4 % |
| Perceptron           | tol=0.005, random_state=0 |1.56s |  85.1 % |
| ComplementNB         |    |1.54s |  83.0 % |
| MultinomialNB        | alpha=1.0|1.58s |  78.8 % |
| Nearest Neighbors    | n_neighbors=6  |1.6s  |  74.7 % |
| Decision Tree        | max_depth=5  |2.56s |  70.9 % |
| Random Forest        | max_depth=5, n_estimators=10, max_features=1  |1.93s |  57.0 % |
| Bagging KNeighbors   | n_neighbors=3, max_samples=0.5, max_features=0.5 |2.4s |  59.3 % |
| AdaBoost             | n_estimators=10 |3.44s |  72.7 % |

AdaBoost amb n_estimators=100 arribava a un score de 82% però tardava molt més temps (20s).

He intentat trobar els millors paràmetres pels 2 millors mètodes:
| Model | Hiperparametres | Temps | Score |
| -- | -- | -- | -- |
| SGDClassifier        | penalty='l2', alpha=0.0001, max_iter=90, tol=0.05 |1.63s |  88.1 % |
| Logistic Regression  | C=4.0, fit_intercept=True, penalty='l2', tol=0.1 | 1.87s |  88.9 % |


## Conclusions
El millor model que s'ha aconseguit ha estat la regressió logística i i el SGD classificador (stochastic gradient descent), els dos amb resultats molt similars, he obtingut un accuracy al voltant de 87%-88%.

El fet d'afegir l'any i el nom del videojoc al model no ha fet millorar gaire els resultats.

Al principi per estalviar temps he entrenat els models sense fer servir totes les paraules, agafant només les que sortien més d'un cert nombre de vegades. Com més paraules s'agafen millor accuracy, per això les he agafat totes.

Al no posar el paràmetre stopwords també s'obtenia millor accuracy, així que vol dir que aquestes paraules també eren importants per la predicció.

## Idees per treballar en un futur
Es poden provar altres models i modificar alguns paràmetres.
També es podria intentar augmentar la mida del dataset amb noves dades.
I també intentar fer un model utilitzant altres paràmetres que es poden calcular a partir de la ressenya de l'usuari, com per exemple, nombre de paraules de la ressenya, nombre d'adjectius positius o negatius, llargada de les frases...
