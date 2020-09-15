brain-pytorch
=============

|GPLv2 license| |Python v3.7| |Stability Experimental| |GitHub issues| |Documentation Status|

A PyTorch implementation of some simplified computing elements from the brain. The elements are according to a somewhat coarse and rudimentary theory on how parts of the brain might work.

.. |GPLv2 license| image:: https://img.shields.io/badge/license-GPL2.0-green?style=for-the-badge
   :target: https://github.com/jeblad/brain-pytorch/blob/master/LICENSE

.. |Python v3.7| image:: https://img.shields.io/badge/python-3.7-blue.svg?style=for-the-badge
   :target: https://www.python.org/

.. |Stability Experimental| image:: https://img.shields.io/badge/stability-experimental-orange.svg?style=for-the-badge
   :target: https://github.com/emersion/stability-badges

.. |GitHub issues| image:: https://img.shields.io/github/issues-raw/jeblad/brain-pytorch?style=for-the-badge
   :target: https://github.com/jeblad/brain-pytorch/issues/

.. |Documentation Status| image:: https://readthedocs.org/projects/brain-pytorch/badge/?style=for-the-badge&version=latest
   :target: https://brain-pytorch.readthedocs.io/en/latest/?badge=latest

Usage
-----

Empty for now.

Development
-----------

This extends the PyTorch library, and the prerequisites for PyTorch (and cuda) should be installed. Please refer to `PyTorch: Get Started <https://pytorch.org/get-started/locally/>`_.

1. Download from `Github <https://github.com/jeblad/brain-pytorch>`_ (`zip <https://github.com/jeblad/brain-pytorch/archive/master.zip>`_) and place the file(s) in a properly named development directory.

2. Change to the development directory and create the environment (with `<PATH>` like `/home/john/.conda/envs/pytorch`)

   .. code:: bash

      conda env create --prefix <PATH> --file conda.yml # possibly with --force

   or

   .. code:: bash

      conda env update --prefix <PATH> --name pytorch --file conda.yml

If necessary, the conda environment can be re-exported with

   .. code:: bash

        conda env export --prefix <PATH> --name pytorch --file conda.yml
