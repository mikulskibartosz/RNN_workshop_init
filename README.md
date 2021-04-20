# Instrukcja dla uczestników warsztatu Tensorflow RNN

## Instalacja na własnym komputerze

1. W wybranym przez siebie managerze pakietów Pythona tworzymy nowe środowisko Python 3.9 i instalujemy następujące pakiety: `pandas, numpy, requests, tensorflow, keras-tuner, scipy, jupyter, matplotlib`. Przy użyciu Pipenv można zrobić to w następujący sposób: `pipenv install --dev pandas numpy requests tensorflow keras-tuner scipy jupyter matplotlib`.
2. Uruchamiany utworzone środowisko (w Pipenv: `pipenv shell`) oraz Jupyter Notebook: `jupyter notebook`).
3. Importujemy wszystkie używany w czasie warsztatu pakiety:
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

import requests

import tensorflow as tf
from tensorflow import keras
from tensorflow.keras import layers
from scipy.stats import zscore
import kerastuner as kt
```
4. Jeśli nie ma żadnego błędu to prawdopodobnie wszystko działa.
5. Pobierz dane których będziemy używać w czasie warsztatu:
```python
r = requests.get('https://raw.githubusercontent.com/mikulskibartosz/RNN_workshop/main/visitors.csv%20-%20Sheet1.csv', allow_redirects=True)
with open('data.csv', 'wb') as f:
  f.write(r.content)
  
data = pd.read_csv('data.csv')
```

## Użycie Google Colab lub Kaggle

Zadania możemy wykonywać uruchamiając kod w Google Colab lub Kaggle. W celu przygotowania środowiska należy utworzyć nowy Notebook i wykonywać kroki z powyższej instrukcji zaczynając od punktu 3.
