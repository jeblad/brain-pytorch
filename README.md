# brain-pytorch

[![LICENSE](https://img.shields.io/badge/license-GPL2.0-green?style=for-the-badge)](https://github.com/jeblad/brain-pytorch/blob/master/LICENSE)
[![Python](https://img.shields.io/badge/python-3.7-blue.svg?style=for-the-badge)](https://www.python.org/)
[![stability-experimental](https://img.shields.io/badge/stability-experimental-orange.svg?style=for-the-badge)](https://github.com/emersion/stability-badges)
[![GitHub issues](https://img.shields.io/github/issues-raw/jeblad/brain-pytorch?style=for-the-badge)](https://github.com/jeblad/brain-pytorch/issues/)
[![Documentation Status](https://readthedocs.org/projects/brain-pytorch/badge/?style=for-the-badge&version=latest)](https://brain-pytorch.readthedocs.io/en/latest/?badge=latest)

A PyTorch implementation of some simplified compute paths from the brain. Compute paths are according to a somewhat coarse and rudimentary theory on how parts of the brain might work. These are best described as [surrogate models](https://en.wikipedia.org/wiki/Surrogate_model) for their postulated behavior.

There are five different compute paths on the automaton (the “brain”) created implicit by these calls

- primary compute path
- lateral compute path
- introspective compute path with external push down automaton
- associative compute path with external correlation automaton
- and the candle layer

Some computing elements may use dependency injection, or give access to default external automatons.

For further descriptions of each computing path, see the upcoming thesis.

## Usage

Import is rather straightforward

```python
import brain
```

Initially a grid with microcolumns are defined on a grid. The grid can be defined with additional fixed-size macrocolumns, or be self-organizing and define the macrocolumns as (or if) necessary.

```python
# create a grid with self-organizing macrocolumns,
# ie. the range of inhibitory connections are unlimited
cortex = brain.grid(123, 456)
# create a grid with self-organizing macrocolumns,
# ie. the range of inhibitory connections are limited
cortex = brain.grid(123, 456, macrosize = 10)
# create a grid with regular-area macrocolumns,
# ie. the range of inhibitory connections are fixed
cortex = brain.grid(123, 456, macrosize-x = 10, macrosize-y = 10)
```

A human has about 2×10⁸ microcolumns, or 200M microcolumns. That is something similar to a call `brain.grid(14142, 14142)`. Not that scary, but unfortunately inside each microcolumn a lot goes on, and we can only achieve a tiny part of the necessary compute power.

In the previous cases only a single microcolumn is injected at each grid cell with some attributes. If necessary, it is possible to adjust the attributes at individual cells

```python
# override the attributes at location (2,3)
cortex[2,3] = brain.attr(macrosize = 20)
```

### Primary compute path

To do something useful compute paths must be injected. The primary compute path is a slightly odd form of residual neural network connected as an autoencoder, but with additional oddities. Suffice to say it will try to reconstruct what pattern exists in the basal layer from the pattern in the apical layer.

Within the boundaries of the grid the primary compute path is set for one or more layers over a part of the cortex

```python
# this will create a primary compute path, consisting of
# five hidden layers of four nodes on each grid cell
cortex[:,:] = brain.primary(4,4,4,4,4)
# this will create a primary compute path, consisting of
# a single layers of four nodes with apical inputs at
# layer 1, basal inputs at layer 3, and implicit output
# on layer 4 on each grid cell
cortex[:,:] = brain.primary(4,apical=1, basal=3)
```

The previous compute path can be closed by a final candle layer, and in many cases routed through convolutional neural layers and a final fully connected layer. Usually this won't be very interesting.

### Lateral compute path

