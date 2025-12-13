# Reconhecimento-de-Jogos

Inteligencia artificial que criei junto ao meu grupo que analiza qual é o jogo por meio de prints, ele utiliza uma CNN pré treinada para fazer a maior parte do trabalho, mas tambem temos uma DenseNet169

Para que funcione, é necessario que voce conecte seu google drive ao colab, alem de colocar esses 2 zips no seu driver no "mydriver", apos isso, apenas rode

Para rodar, comole o .ipynb no google colab, conecte-se a uma GPU (pode ser a T4) e espere rodar o codigo

- "Quero adicionar mais um video para ele analizer"

Caso queria adicionar videos, entre no zip "videos_teste" e adicione um video que deseje, para economia de tempo, a IA escolhe um video aleatório, portanto voce pode apagar os outros videos que estão nesta pasta e colocar o video que deseja, quanto menor o video menor o tempo para o resultado cair, exemplo:

- Video de 1 hora: aproximadamente 1 hora e 30 para sair o resultado

Por fim, caso voce ja tenha treinado a IA uma vez, n será necessário reiniciar toda a IA, apenas faça a troca do video_teste e acione a ultima intancia do codigo, ele começa assim:

```bash
import cv2
import numpy as np
import tensorflow as tf
import os
import random
import zipfile
from google.colab import drive
from collections import deque
from IPython.display import clear_output

ZIP_NAME = 'videos_teste.zip'  
DRIVE_PATH = f'/content/drive/MyDrive/{ZIP_NAME}'
EXTRACT_PATH = '/content/videos_aleatorios_temp'
QUEUE_SIZE = 30 
VIDEO_SIZE_OUTPUT = (1280, 720)
FONT = cv2.FONT_HERSHEY_SIMPLEX
```