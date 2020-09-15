# Install

This extends the PyTorch library, and the prerequisites for PyTorch (and cuda) should be installed. Please refer to [PyTorch: Get Started](https://pytorch.org/get-started/locally/).

## PIP Install

1. Download from [Github](https://github.com/jeblad/brain-pytorch) ([zip](https://github.com/jeblad/brain-pytorch/archive/master.zip)) and place the file(s) in a properly named development directory.

2. Change to the development directory and create the environment by running one of
	```bash
	pip install -r requirements.txt
	```

## Conda Install

1. Download from [Github](https://github.com/jeblad/brain-pytorch) ([zip](https://github.com/jeblad/brain-pytorch/archive/master.zip)) and place the file(s) in a properly named development directory.

2. Change to the development directory and create the environment by running one of

	```bash
	conda env create --file conda.yml # possibly with --force
	conda env create --prefix <PATH> --file conda.yml # with `<PATH>` like `/home/john/.conda/envs/pytorch`
	```

	or

	```bash
	conda env update --prefix <PATH> --name brain-pytorch --file conda.yml
	```

3. Activate the environment

	```bash
	conda activate brain-pytorch
	```

The conda environment can be re-exported with

```bash
conda env export --prefix <PATH> --name brain-pytorch --file conda.yml
```

## Simple Tests

A simple check on a working environment (run this in an interactive `python` shell)

```Python
>>> import torch
```

This will give an error message if torch is not found in the environment.

A simple check on a working PyTorch installation

```Python
import torch
>>> >>> x = torch.rand( 3 )
>>> print( x )
tensor([0.0889, 0.0143, 0.4892])
```

This will give a tensor as output if torch is working properly.

A simple check to see if CUDA is available

```python
import torch
>>> torch.cuda.is_available()
True
```

This will give a boolean true if CUDA is found and working properly. Still, it might give true even if a GPU is missing.

A simple check to see if GPU is visible from pytorch

```Python
import torch

>>> torch.cuda.current_device()
0

>>> torch.cuda.device(0)
<torch.cuda.device object at 0x7f7555a4db90>

>>> torch.cuda.device_count()
1

>>> torch.cuda.get_device_name(0)
'GeForce GTX 960'
```

All example output can be different for an actual run.
