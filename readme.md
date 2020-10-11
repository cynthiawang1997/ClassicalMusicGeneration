# Classical Piano Music Generation with Deep Learning

## Objective
This project aims to generate classical music with deep learning.
​
## Methodology
​
### Data Collection
316 midi files from http://www.piano-midi.de/. The average duration of the songs is 4 minutes.

### Data Preprocessing
Unlike audio files that contain the actual music, midi files contain instructions of playing the music. Midi files are parsed using pretty_midi package. Each song is converted into a piano roll array that represents the notes played at each time step. The piano roll array is then converted into a dictionary with time steps as keys and notes played at the corresponding time steps as values. An index is assigned to each unique note or chord and saved in a dictionary. Using this dictionary, I could get a dictionary of time steps and the indices of notes played. To prepare the input data for neural networks, I extract training windows and the target notes. In the model, I use 50 consecutive time steps to predict the note/chord played at the next time step (i.e. the 51st time step). A total of 1.5 million training windows are extracted from 316 songs. 

### Model Architecture
- embedding layer 
- bidirectional GRU layers
- self-attention layers
- dropout layers

### Technology
- Neural Networks
- Tensorflow
- Keras
  - LeakyReLU
  - Embedding
  - Bidirectional GRU
  - Self-attention
  - Dropout
- pretty_midi
- pickle 
- seaborn
- numpy
- re
- pypianoroll
- tqdm
- Google Cloud Platform


## Deliverables
- Jupyter notebooks for 
  - Data preprocessing
  - Model training with 10 epochs 
  - Model training with 20 epochs 
  - Music training with Chopin
  - Music generation (all songs)
- Folder for sample midi files from generation
- Folder for sample midi files from dataset 
- Presentation deck