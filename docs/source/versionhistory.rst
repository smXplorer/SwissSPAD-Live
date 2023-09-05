Version History
===============

v 0.7.2 (2023-09-04)
--------------------

- Bug Fixes

    + Fixed bug on first run if hot pixel removal is selected
    
- New Feature

    + grayed out "SS3 Hot Pixel Mismatch Detection" option in Settings >> File 
      Information

v 0.7.1 (2023-09-02)
--------------------
- Bug Fixes

    + Fixed bug in default selected half
    + Added missing Settings initialization

- New Features

    + Reverted some of the Settings Window changes
    + Changed Displayed Image list to G2 Gate, INT Gate and INT - G2 for clarity
    + Histogram Window now closes when SwissSPAD Live quits
    + Settings Window now closes when SewissSPAD Live quits
    + Enabled Gated Mode during Live Mode
    
v 0.7 (2023-08-09)
------------------
- Bug Fixes

    + Fixed file version string typo
    + Fixed "Use Histogram Cursors for Contrast"
    
- New Features

    + Added support for initialization of two FPGAs
    + Added option to select which half array is displayed in Live Display
    + Introduced SwissSPAD Live HDF5 File version 0.7
    + Added "Microlens" checkbox in DAQ Parameters
    + Added "Gate Image Integration" and replaced "Exposure/Gate" by "Gate Image
      Exposure"
    + Added support for hot pixel mask image
    + Added UI Settings option to use the Image Display Options for the Histogram
      (i.e. use Hot Pixel Removal)
    + Added Verbose Settings & Verbose Saving options in UI Settings
    + Added option to Save Sum of All Gates Preview Images

v 0.6 (2022-12-05, unreleased)
------------------------------
- Bug Fixes:

    + Save Image Data as TIFF now opens file dialog in last used folder
    + Fixed a typo in the "SwissSPAD Detector Information" group name
    + Improved error handling upon FPGA timeout
    + Fixed exposure time formula for SS2

- New Features:

    + Vision Development Module-free version released as executable
    + Added Cursors to Histogram and option to use them to adjust image contrast
    + Changed split bar layout
    + Added Image Display Options in Settings->Image Parameters
    + Implemented "Remove Outliers" for Displayed Image
    + Changed SS3 Gate Definition parameter from Duty Cycle to Gate Width
    + Changed "Use Duty Cycle" checkbox to "Gate Definition"
    + Added "Use Ducty Cycle" checkbox to SS3 DAQ Parameters
    + Added extraction of FPGA clock base from bitfile file name
    + Added SS3 Gate Slippage Correction option
    + Changed buffer size unit to "# 8-bit Gates". The best value appears to be 1.
    + Added Error Dialog in Notebook when loading of a rtf file fails
    + Upgraded to LabVIEW 2021 SP1
    + Modification of HDF5 File Format to support Gate Names
    + Improved Settings Window initialization
    + Added "Save Image Data as TIFF" right-click menu item
    + Added "Connect" button and "Connected" LED in Settings>>FPGA
    + Added "Intensity Mode" option in Settings >> SS3 DAQ Parameters
    + Added "Image to Display" option in Settings >> Image Parameters (Gate 1, 
      Gate 2, Gate 1 + Gate 2)
    + Added gate shift directionality option
    + Implemented SS3 gate characteristics
    + Added FPGA S/N to Detector version database
    + Introduced bitfile version from bitfile content

v0.5.2 (2021-08-20)
-------------------
- Bug Fixes:

    + Option to add an underscore addition to the file name includes cases where
      the number of gates saved is not equal to the target
    + Actual number of saved gates reported in the Notebook now is correct

v 0.5 (2021-07-22)
------------------
- Bug Fixes:

   + Fixed some typos

- New Features:

    + Added Sync Period, MAC Address and Windows username to HDF5 header >> 
      version 0.5 of SwissSPAD 2 HDF5 File Format
    + Added option to add underscore to scrambled dataset file names
    + Added option to insert delay between series datasets
    + Added PCB1 vs PCB2 check for scrambling test implementation (to be improved)
    + Implemented Compression Level Option

v 0.4 (2021-04-06)
------------------
- Bug Fixes:

    + Fixed *Abort All Saving Tasks* action

- New Features:

    + Added *Reset FPGA* Help menu item
    + Open Notebook on startup and check for saved  Notebook status upon quitting

v 0.3.4 (2021-04-05)
--------------------
- Bug Fixes:

    + Fixed a bug in scrambled data test

v 0.3.3 (2021-04-04)
--------------------
- Bug Fixes:

    + Fixed handling of Admin-protected Gate Definitions
    + Debugged Gate Definition UI

- New Features:

    + Added Notebook warning when data was scrambled during transfer
