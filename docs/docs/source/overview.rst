Overview
========

SwissSPAD Live is an open source LabVIEW program written by X. Michalet at UCLA, supporting data acquisition with the SwissSPAD 2 (SS2) & SwissSPAD 3 (SS3) 
time-gated SPAD arrays developed by Arin Ulku in the `Aqua Lab <https://www.epfl.ch/labs/aqua/>`_ 
of Prof. Edoardo Charbon at EPFL.
The SS2 detector and some of its applications are described in refs. [1]_, [2]_,
[3]_ \& [4]_,
while SS3 is described in refs. [5]_ \& [6]_

SwissSPAD Live is based on MATLAB scripts calling different versions of the FPGA firmware developed by Arin (bitfiles). The bitfiles provided as part of this distribution are Arin's, the LabVIEW code simply uploading and starting them to accomplish the necessary data acquisition and transfer tasks, and is intended to simplify:

+ definition of acquisition parameters

+ live preview

+ data acquisition monitoring

+ data saving (individual datasets and series)

+ experiment documentation and logging

Datasets are saved in the AlliGator HDF5 file format documented in :ref:`alligator-hdf5-file-format`.

This manual provides an overview of the different windows constituting the GUI
and of the corresponding actions they help perform.
Please refer to the corresponding chapters for further information.


.. [1] A. C. Ulku et al., (2018). "A 512 × 512 SPAD Image Sensor With Integrated
 Gating for Widefield FLIM," in IEEE Journal of Selected Topics in Quantum 
 Electronics, vol. 25, no. 1, pp. 1-12, Jan.-Feb. 2019, Art no. 6801212, DOI: `10.1109/JSTQE.2018.2867439 <https://doi.org/10.1109/JSTQE.2018.2867439>`_

.. [2]  A. C. Ulku et al., (2020). "Wide-field time-gated SPAD imager for phasor
 -based FLIM applications", Methods and Applications in Fluorescence, Volume 8, 
 Number 2, Art no. 024002, DOI: `10.1088/2050-6120/ab6ed7 <https://doi.org/10.1088/2050-6120/ab6ed7>`_

.. [3] R. Ankri et al., (2020). "Single-Photon, Time-Gated, Phasor-Based 
 Fluorescence Lifetime Imaging through Highly Scattering Medium", ACS Photonics, 
 Volume 7, Issue 1, page 68–79, DOI: `10.1021/acsphotonics.9b00874 <https://doi.org/10.1021/acsphotonics.9b00874>`_

.. [4] J. T. Smith et al., (2022). "In vitro and in vivo NIR Fluorescence 
 Lifetime Imaging with a time-gated SPAD camera", Optica, Volume 9, Issue 
 5, page 532-544, DOI: `10.1364/OPTICA.454790 
 <https://doi.org/10.1364/OPTICA.454790>`_

.. [5] M. Wayne et al., (2022). "A 500 × 500 Dual-Gate SPAD Imager With
 100% Temporal Aperture and 1 ns Minimum Gate Length for FLIM and Phasor
 Imaging Applications", IEEE Transactions on Electron Devices, Volume 69, Issue 
 6, page 2865-2872, DOI: `10.1109/TED.2022.3168249 <https://doi.org/10.1109/TED.2022.3168249>`_
 
.. [6] X. Michalet et al., (2023). "NIR fluorescence lifetime macroscopic 
 imaging with a novel time-gated SPAD camera", Proceedings of SPIE, Volume 12384
 , Article 1238409, DOI: `10.1117/12.2649227 <https://doi.org/10.1117/12.2649227>`_
 