# Automatic Model Evolution

Small-scale experiments evolving optimal ML models for ICE raid predictions.

El pueblo unido jamás será vencido.

### Getting started

Download [Python3](https://www.python.org/downloads/).

Download our Python dependencies.

```bash
pip3 install -r requirements
```

Download the Syracuse TRAC ICE Arrests dataset *(optional)*:

```bash
python3 datasetgenerator.py
```

Train a ML model *(optional)*:

```bash
python3 ai.py
```

Evolve an optimal ML model:

```bash
python3 evolve.py
```

### Structure

The backend is divided up into a number of files:

- `datasetgenerator.py`

>  Uses its `Syracuse` class to create a dataset of ICE arrests in the US and saves it to `data.csv`.

- `ai.py`

> Builds and trains an LSTM model on `data.csv`. It uses the model and dataset to predict future arrests and saves them to `predictions.csv`.


- `evolve.py`

> Leverages evolution to find the optimal model by evolving a population of deep learning models with a low test error.

### Dependencies:

- requests
- pandas
- Flask
- geopy
- keras==2.2.5
- Tensorflow==2.0.1
- progress
