.. _user-guide:

User Guide
==========
.. _live-mode:

Live Mode
---------

Overview
^^^^^^^^

The ``Live Mode`` is intended for rapid acquisition of full-frame images for alignment purpose or to check the signal level.

In this mode, the following parameters defined in the ``Acquisition Parameters`` tab of the ``Settings`` window are ignored and replaced by the following values:

- 10 bits: FALSE

- # Sets: 1

If the bitfile is an 'intensity' one, of course all gate definition parameters (``Gate Offset``, ``gs_psincdec_n`` and ``gs_no_shift_adj``) are also ignored.

Details
^^^^^^^

To start a Live Acquisition, simply click the ``Start`` button (bottom right).

During Live Acquisition, a 'busy' icon is displayed next to the Record button.

To stop a Live Acquisition, click on the same button (now labeled ``Stop``).

While you will be warned to do so, remember to stop a Live Acquisition before starting a Recording (or quitting).
	
.. _recording-mode:

Recording Mode
--------------

Overview
^^^^^^^^

To start recording, click on the ``Record`` button (to the right of the ``Start`` button).

During recording, a 'busy' icon is displayed next to the Record button.

In addition, a ``Saving in progress`` LED is turned on, indicating that data is being saved in the background. Hovering over this LED with the mouse will display information on the on-going saving task(s) in the Context Help window: ``File Name: current/total Images, File Size in MB``. Checking this information is useful to monitor the progress of data saving, but also to detect a potential FPGA communication problem, e.g. if one of the files is stuck at 0 image.

The acquisition can be aborted by clicking on the same button, now labeled ``Abort``.

Data saving can be interrupted by right-clicking on the ``Saving in progress`` LED and selecting ``Abort All Saving Tasks``.

Details
^^^^^^^

A recording consists in the acquisition of a user-specified number ``S`` (default: 1) of gate sets (parameter ``# Sets`` in the :ref:`Acquisition Parameters <acquisition-parameters-tab>` tab of the Settings window), each set comprising a user-specified number ``g`` of gates (parameter ``# Gates per Set``).

The ``G = S x g`` gates are shifted with respect to one another by ``Gate Shift`` increments of ``dt = 1/56 ns`` (*i.e* 17.8571 ps), the first gate starting at an offset specified by ``Gate Offset`` (in 1/56 ns units). The complete series of gates thus covers a span of ``G x dt`` reported as ``Gate Images Span`` in the :ref:`Acquisition Parameters <acquisition-parameters-tab>` tab of the Settings window.

The data stored on the FPGA is continuously transfered to the PC, decoded and saved in parallel, which can result in the data acquisition being over well before the data is fully saved. This is why three different completion messages are printed in the Notebook:

- a data transfer completion message

- a data decoding completion message

- a data file saving completion message

A new data recording can be started as soon as the previous one is completed, even if the corresponing data saving task is still on-going. For this reason, it is important to check the status of the LED on the main window, as data saving can significantly lag behind data acquisition (i.e. do not quit until all your data is saved!). Note that not checking the ``Compression`` checkbox in the :ref:`File Information <file-information-tab>` tab of the Settings window may speed up data saving, at the expense of significantly larger files (5x or more).

.. _setting-acquisition-parameters:

Setting Acquisition Parameters
------------------------------

Besides the gate definitions parameters discussed above, the following parameters can be modified:

- ``10 bits``: by default, data is stored as the sum of 255 1-bit images. When checking this checkbox, 4 such images are acquired and transfered to the PC, and accumulated before saving (or displaying) the data. The maximum pixel value is therefore 1,020. Data acquisition takes 4 times longer than for an 8-bit image.

- ``# Exposure Sequences``: this parameter specifies during how many laser periods the gare is opened and closed for each 1-bit gate image. Adjust this parameter by checking the :ref:`Histogram Window <histogram-window>` and trying to make sure the largest value stays away from the maximum (either 255 or 1,020) to avoid saturation. Large values (> 100) also result in readout artifacts and should be avoided.

- ``Laser Period``: this information is saved in the file for the user's convenience but has no impact on acquisition.

- ``Buffer Size (# Gates)``: this parameter controls the size of FPGA memory that is transfered as a block to the PC. Too large a value will result in long transfer times and might end up in the FPGA FIFO overfilling while transfer of the previous block ends.

Too small a value may result in the FIFO overfilling because of a MS Windows interrupt preventing it to be emptied on time. This can result in two different types of symptoms:

	* The acquisition is interrupted after a 10 s pause, and results in an error message (in red) in the Notebook. See :ref:`Troubleshooting <troubleshooting>` for further details.

	* The acquisition is not interrupted, but a warning message in red is displayed in the Notebook, according to which data has been scrambled during transfer. See :ref:`Troubleshooting <troubleshooting>` for further details.

- ``Preset Configuration``: This pull-dowm menu gives access to 7 preset gate parameters configurations tested by EPFL. The parameters set by these configurations are the 4 ``gs_psincdec`` and the 3 ``gs_no_shift_adj`` parameters, whose definition can be found in Arin Ulku's Ph D thesis. In a nutshell, they define the gate size, which is reported in the ``Predicted Gate Width`` below. These parameters cannot be modified by the user (see :ref:`note <gate-configuration-admin>` below).

Note that the ``Gate Offset`` parameter for these preset configurations is set to zero, but can be changed by the user. In that case, the preset configuration changes to ``User-defined configuration``. To store such a choice (gate configuration + offset) for future use, right-click the pull-down menu and select among the different menu options.

A good starting value is 20, depending on PC performance (reducing the number of active or background processes such as Wimdows Telemetry, File Indexing, etc., may help with performance).

.. _gate-configuration-admin:

**Note**: If needed, it is possible to modify the protected gate configuration parameters in 'Admin' mode, turned on in the :ref:`About Window <about-window>`.

.. _opening-hdf5-files:

Opening HDF5 Files
------------------

The HDF5 format in which series of gate images are saved is described on the AlliGator software website:

https://sites.google.com/a/g.ucla.edu/alligator/alligator-technical-reference/alligator-hdf5-file-format

AlliGator can be used to open and analyze HDF5 files saved by SwissSPAD Live.

.. _troubleshooting:

Troubleshooting
---------------

.. _troubleshooting-manual:

Manual issues
^^^^^^^^^^^^^

If you find issues with this manual (typo, error, obscurity, etc.) or have suggestions for its improvement, please create an issue on the ``SS2 Live Manual`` Bibucket repository at `<https://bitbucket.org/smXplorer/ss2-live-manual/issues?status=new&status=open>`_.

.. _troubleshooting-software:

Software issues
^^^^^^^^^^^^^^^

If you find issues with the software itself (persistent error, bug, etc.) or want to suggest features for future releases, please join the ``SwissSPAD Live Support`` Google Group at `<https://groups.google.com/g/swissspad-live-support>`_.

.. _troubleshooting-problems:

Common problems
^^^^^^^^^^^^^^^
The following is a list of common issues that may be encountered and possible workarounds.

**Important Note: don't forget to open the Notebook! Oftentimes, there is a lot of information printed there (in red) about errors, which might sometimes help diagnose the source of the problem.**

Live acquisition or Data recording does not work anymore
""""""""""""""""""""""""""""""""""""""""""""""""""""""""

1. When the FPGA FIFO overfills, the FPGA sometimes enters into an unrecoverable state and times out after 10 s, resulting in a corresponding error code sent to the Notebook. To recover from this situation use the ``Help >> Reset FPGA`` menu item.

2. It might in some cases be necessary to stop SwissSPAD Live and restart it. If that still does not solve the issue, quitting and restarting LabVIEW might be necessary.

3. Finally, occasionally the following steps may still not be sufficient to re-establish communication with the FPGA, necessitating a reboot of the FPGA. To do this, first stop SwissSPAD Live and simply unplug and then immediately plug back the FPGA power supply from its wall socket.

Note that in order to not lose the information stored in the Notebook, it is a recommended to save it before quitting SwissSPAD Live and LabVIEW. Then, immediately after restarting SwissSPAD Live, reopen that saved file within the Notebook, so that the remainder of the experiment is appended to the current log.

There was a warning after a recording completed
"""""""""""""""""""""""""""""""""""""""""""""""

Occasionally, transfer from the FPGA fails to keep up insidiously and does not return a timeout error, resulting in data blocks to become out of sync. The missing chunks of data will in general leave the dataset impossible to use, hence the warning.

It is recommended to record the data again, possibly after changing some of the acquisition parameters, or verifying that the PC is not busy with other tasks, sources of potential interrupts.

Data saving is stuck
""""""""""""""""""""

When all recordings are complete but data saving seems to take an inordinate amount of time, check the data saving status by hovering over the status LED at the bottom of the main window and check the context Help window. If the last listed files is stuck at 0/n images, then most likely a FIFO overflow occurred and the FPGA is in an unrecoverable mode. Abort all savings tasks (if needed also first abort recording) and follow the instructions in the previous paragraph.

Images are all black
""""""""""""""""""""

Verify that the SwissSPAD power supplies are turned on.
