# Automatic Model Evolution

Evolving ML models for ICE raid predictions.

## Getting started

Download [Python3](https://www.python.org/downloads/).

Download our Python dependencies.

```bash
pip3 install -r requirements
```

Evolve an optimal ML model on data.csv *(cool)*:

```bash
python3 evolve.py
```

Train a single ML model on data.csv *(boring)*:

```bash
python3 model.py
```

## Files

### `evolve.py`

> Leverages evolution to find the optimal model on ICE raid time-series
predictions by generating a population of deep learning models, assigning them a
fitness according to their test loss and recombining them to create a next
generation of models.

The entry point of the application. To use AME, initialize it:

```Python
ame = AutomaticModelEvolution()
ame.run()
ame.save()
```

### `model.py`

> Builds and trains an LSTM model on `data.csv` given its parameters.
Is serializable into a mutatable object.

```Python
model = Model()
model.fit()
```

### Dependencies:

- requests
- pandas
- Flask
- geopy
- keras==2.2.5
- Tensorflow==2.0.1
- progress
