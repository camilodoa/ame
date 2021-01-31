# Automatic Model Evolution

Evolving ML models for ICE raid predictions. Models are an extra layer of
abstraction on top of [Keras](https://keras.io/).

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

Arguments:
- size: Int: number of individuals

- generations: Int: number of iterations to run

- ancestor: Boolean: whether to add previously found optimal model to population

- target: Float: target error to reach

- mutation: Float 0-1: mutation frequency

- addition_rate: Float 0-1: new layer addition frequency for every model

- deletion_rate: Float 0-1: layer removal frequency for every model

- layer_options: Dict: {name: object} dict of available layer types

- verbose: Bool as 0,1 : whether to use additional debugging print statement


The entry point of the application. To use AME, initialize it:

```Python
ame = AutomaticModelEvolution()
fittest = ame.run()
```

### `model.py`

> Builds and trains an LSTM model on `data.csv` given its parameters.
Is serializable into a mutatable object.

```Python
model = Model()
history = model.fit()
```

### Dependencies:

- requests
- pandas
- Flask
- geopy
- keras==2.2.5
- tensorflow==2.0.1
- progress
