# brain-pytorch

[![LICENSE](https://img.shields.io/badge/license-GPL2.0-green?style=for-the-badge)](https://github.com/jeblad/brain-pytorch/blob/master/LICENSE)
[![Python](https://img.shields.io/badge/python-3.7-blue.svg?style=for-the-badge)](https://www.python.org/)
[![stability-experimental](https://img.shields.io/badge/stability-experimental-orange.svg?style=for-the-badge)](https://github.com/emersion/stability-badges)
[![GitHub issues](https://img.shields.io/github/issues-raw/jeblad/brain-pytorch?style=for-the-badge)](https://github.com/jeblad/brain-pytorch/issues/)
[![Documentation Status](https://readthedocs.org/projects/brain-pytorch/badge/?style=for-the-badge&version=latest)](https://brain-pytorch.readthedocs.io/en/latest/?badge=latest)

A PyTorch implementation of some simplified computing elements from the brain. The computing elements are according to a somewhat coarse and rudimentary theory on how parts of the brain might work. These are best described as [surrogate models](https://en.wikipedia.org/wiki/Surrogate_model) for postulated behavior.

There are five different computing elements, or computing paths, on the automaton created implicit by these calls

- primary path
- lateral path
- introspective path with external push down automaton
- associative path with external correlation automaton
- candle layer

Some computing elements may use dependency injection, or give access to default external automatons.

For further descriptions of each computing path, see the upcoming thesis.

## Usage

The primary path defines one or more layers in microcolumns on a grid. The grid can be defined with additional macrocolumns, or be free-running and define the macrocolumns as (or if) necessary.

```python
import brain
import brain.primary as bp
import brain.lateral as bl
import brain.introspective as pi
import brain.associative as pa
import brain.candle as pc
```

