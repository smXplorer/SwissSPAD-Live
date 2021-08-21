Overview
========

SwissSPAD Live is an open source LabVIEW program written by X. Michalet at UCLA, supporting data acquisition with the SwissSPAD 2 time-gated SPAD array developed by Arin Ulku
from the `Aqua Lab <https://www.epfl.ch/labs/aqua/>`_ (Prof. Edoardo Charbon) at EPFL. The detector and some of its applications are described in refs. [1]_, [2]_ and [3]_.

| It is based on the different versions of the Xilinx FPGA firmware developed by Arin, and is intended to simplify:

- acquisition parameter selection
- data saving (individual datasets and series)
- experiment documentation and logging

Datasets are saved in the AlliGator HDF5 file format documented `here <https://sites.google.com/a/g.ucla.edu/alligator/alligator-technical-reference/alligator-hdf5-file-format>`_.

| This manual provides an overview of the different windows consituting the GUI and of the corresponding actions they help perform.

Please refer to the corresponding chapters for further information.


.. [1] A. C. Ulku et al., (2018). "A 512 × 512 SPAD Image Sensor With Integrated Gating for Widefield FLIM," in IEEE Journal of Selected Topics in Quantum Electronics, vol. 25, no. 1, pp. 1-12, Jan.-Feb. 2019, Art no. 6801212, DOI: `10.1109/JSTQE.2018.2867439 <https://doi.org/10.1109/JSTQE.2018.2867439>`_

.. [2]  A. C. Ulku et al., (2020). "Wide-field time-gated SPAD imager for phasor-based FLIM applications", Methods and Applications in Fluorescence, Volume 8, Number 2, Art no. 024002, DOI: `10.1088/2050-6120/ab6ed7 <https://doi.org/10.1088/2050-6120/ab6ed7>`_

.. [3] R. Ankri et al., (2020). "Single-Photon, Time-Gated, Phasor-Based Fluorescence Lifetime Imaging through Highly Scattering Medium", ACS Photonics, Volume 7, Issue 1, page 68–79, DOI: `10.1021/acsphotonics.9b00874 <https://doi.org/10.1021/acsphotonics.9b00874>`_