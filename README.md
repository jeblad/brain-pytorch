# brain-pytorch

[![LICENSE](https://img.shields.io/badge/license-GPL2.0-green?style=for-the-badge)](https://github.com/jeblad/brain-pytorch/blob/master/LICENSE)
[![Python](https://img.shields.io/badge/python-3.7-blue.svg?style=for-the-badge)](https://www.python.org/)
![stability-experimental](https://img.shields.io/badge/stability-experimental-orange.svg?style=for-the-badge)
![GitHub issues](https://img.shields.io/github/issues-raw/jeblad/brain-pytorch?style=for-the-badge)

A PyTorch implementation of some simplified computing elements from the brain. The elements are according to a somewhat coarse and rudimentary theory on how parts of the brain might work.

## Usage



## Development

This extends the PyTorch library, and the prerequisites for PyTorch (and cuda) should be installed. Please refer to [PyTorch: Get Started](https://pytorch.org/get-started/locally/).

1. Download from [Github](https://github.com/jeblad/brain-pytorch) ([zip](https://github.com/jeblad/brain-pytorch/archive/master.zip)) and place the file(s) in a properly named development directory.

2. Change to the development directory and create the environment (with `<PATH>` like `/home/john/.conda/envs/pytorch`)

	```bash
	conda env create --prefix <PATH> --file conda.yml # possibly with --force
	```

	or

	```bash
	conda env update --prefix <PATH> --name pytorch --file conda.yml
	```

The conda environment can be re-exported with

	```bash
	conda env export --prefix <PATH> --name pytorch --file conda.yml
	```
