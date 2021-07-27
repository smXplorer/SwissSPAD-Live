Installation
============

**Important Note: This software package runs exclusively on Windows 64 bits (version 7 and up).**

Installation requires a number of steps, some of which may not be necessary if you have the corresponding software already installed, or do not need to be repeated for subsequent updates:

- LabVIEW Full Development System Installation

- Vision Development Module Installation

- JKI VI Package Manager Installation

- Open G Toolkit Installation

- GOOP Development Suite Installation

- HDF5 LabVIEW Binding Installation

- Opal Kelly Front Panel SDK

- Repository installation

These different steps are detailed below.

LabVIEW Full Development System Installation
--------------------------------------------

A valid license for LabVIEW 2019 SP1 64 bit is needed to run this software (while later versions might be compatible, they have not been tested). The installer itself can be found at: `<https://www.ni.com/en-us/support/downloads/software-products/download.labview.html>`_.

Please make sure you select the correct version (2019 SP1, Base, Full, Professional) AND 64 bit. No additional toolkit (except for the Vision Development Module and JKI VI Package Manager see below) is needed.

Vision Development Module Installation
--------------------------------------

A valid license for the Vision Development Module 2019 SP1 is needed to run this software (while later versions might be compatible, they have not been tested). The installer itself can be found at: `<https://www.ni.com/en-us/support/downloads/software-products/download.vision-development-module.html#367068>`_, in case you have not selected it as one of the optional addons during LabVIEW installation.

Please make sure you select the correct version (2019 SP1, Full). The module install both 32 and 64 bit versions.

JKI VI Package Manager Installation
-----------------------------------

The JKI VI Package Manager (VIPM) simplifies the installation of the two subsequent packages and is free. It is offered as one of the optional addons during LabVIEW installation. If you omitted to select it at the time (or have LabVIEW already installed), its installer can be found here: `<https://www.vipm.io/download/>`_. The version doesn't really matter and will probably be posterior to 2019 by the time your read these lines.

Open G Toolkit Installation
---------------------------

- Run JKI VIPM. The first time on, repositories are scanned and packages downloaded, which may take some time.

- Once this is done, type 'Open G Toolkit' in the Search Box. This should result in a single item showing up in the package list. Select and install it (accept all defaults in subsequent dialogs). Installation of the Toolkit will launch LabVIEW and require some lengthy download and compilation. Please let this process come to completion.

Keep VIPM and LabVIEW open as they will be needed for the next step.

HDF5 LabVIEW Binding Installation
---------------------------------

HDF5 support is provided by the wrapper developed by Martijn Jasperse and available at `<http://h5labview.sourceforge.net/>`_. 

- The first step in the installation consists in downloading the HDF5 library per se. A copy of the installer (for the supported version) is conveniently available on the previous website at: `<https://support.hdfgroup.org/ftp/HDF5/releases/hdf5-1.8/hdf5-1.8.18/bin/windows/extra/hdf5-1.8.18-win64-vs2015-shared.zip>`_

- Download the zip file, expand it and run the .msi installer to install the HDF5 library.

- Once this is done, download the VIPM package at: `<https://sourceforge.net/projects/h5labview/files/h5labview2-2.13.1.143.vip/download>`_

- Go to VIPM and load the .vip package you just downloaded (File >> Open Package File(s)).

- Install the package you just loaded into VIPM (or if you postpone this task to later on, search for the package using 'h5labview').

Opal Kelly Front Panel SDK
--------------------------

To communicate with SwissSPAD 2's FPGA, the software needs a development toolkit provided by Opal Kelly. While the SDK is free, you will need to register to be able to download and install it.

Navigate to `<https://pins.opalkelly.com/users/sign_up>`_ to register.

Once you have registered and logged in, navigate to `<https://pins.opalkelly.com/downloads>`_ to find the download link.

The FrontPanel SDK installer will show up only if you are registered and logged in and should appear as "FrontPanelUSB-Win-x64-x.y.z.exe" were x.y.z is the version. SwissSPAD Live has been tested with version 5.2.3, but should work with later versions too.

Download the installer and install the SDK (default settings).

To verify that the installation proceeded correctly, connect SwissSPAD2's USB 3 cable to the computer and power up the FPGA (there is no need to power up SwissSPAD 2 itself for this test). Find the FrontPanel application (Start Menu >> Opal Kelly >> FrontPanel) and run it. It should show a connected board. Quit the application.


Repository Installation
-----------------------

	The source repository is located at:

`<https://bitbucket.org/smXplorer/ss2-live-distribution>`_

You can either clone the repository (so that you are informed of any updates and easily can try them out) or simply download the entire repository (~7 MB zipped, ~40 MB expanded) and expand it in the folder of your choice.

*Warning 1*: It is possible that the two DLL's normally present in the Opal Kelly >> C# Wrapper folder are missing. In that case, download them individually from the repository and save them in the C# Wrapper folder.

*Warning 2*: By default, the DLL's may end up in a "locked" state, which will prevent their usage by SwissSPAD Live. Before running LabVIEW and SwissSPAD Live, make sure they are "unlocked". To do so, navigate to the C# Wrapper folder with Windows Explorer and right-click on the dll files, choosing "Properties". As explained in `this article <https://knowledge.ni.com/KnowledgeArticleDetails?id=kA00Z0000019UnoSAE&l=en-US>`_, the DLL's are probably "locked" and will need to be unlocked.

Opening SwissSPAD2 Live.vi
--------------------------

When first opening SwissSPAD2 Live.vi (make sure this is done using LabVIEW 2019 SP1 64 bit or above), LabVIEW will most likely be looking for VIs. It should be rather straightforward to guide it to the correct directory. If not, create an Issue using the tool provided in the repository (look for 'Issues' on the left hand side menu on the repository main page).

Run the VI.

For further information on how to use the software, check the :ref:`User Guide <user-guide>`. 