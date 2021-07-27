Version History
===============

v 0.5 (2021-07-22)
------------------
- Features:

    + Added Sync Period, MAC Address and Windows username to HDF5 header >> version 0.5 of SwissSPAD 2 HDF5 File Format
	
    + Added option to add underscore to scrambled dataset file names

    + Added option to insert delay between series datasets

    + Added automatic FPGA Reset Attempt Flag in Settings
	
	+ Added PCB1 vs PCB2 check for scrambling test implementation (to be improved)
	
    + Implemented Compression Level Option
	
- Bug Fixes:

   + Fixed some typos

v 0.4 (2021-04-06)
------------------
- Features:

	+ Added *Reset FPGA* Help menu item
	
	+ Open Notebook on startup and check for saved  Notebook status upon quitting

- Bug Fixes:

	+ Fixed *Abort All Saving Tasks* action

v 0.3.4 (2021-04-05)
--------------------
	
- Bug Fixes:

	+ Fixed a bug in scrambled data test


v 0.3.3 (2021-04-04)
--------------------

- Features:

	+ Added Notebook warning when data was scrambled during transfer

- Bug Fixes:

	+ Fixed handling of Admin-protected Gate Definitions
	
	+ Debugged Gate Definition UI 