# PiSpec20_stellarnet
A Python interface for StellarNet spectrometers designed to provide the functions of a Spectronic 20 spectrophotometer
## Project Goals and Motivations  
The goal of this project was to replace the old Spec 20s in our teaching laboratories with equivalent functionality in 
modern equipment.  Choices of hardware and software were driven largely by familiarity.  The choice of the Raspberry Pi was 
to make an effectively disposable computer.  I picked Python 3.x (works on Python 2.7 also) for simplicity in migrating to different hardware.  What I created here is a simple frontend for the spectrometer suitable for use by relatively untrained undergraduate students.
## Project Audience  
The project was written to support undergraduate laboratories, so really this repository is for people looking for a frontend 
to run their spectrometer.  However, the functionality of the project can readily be expanded to take advantage of the 
spectrometer features.  This code takes care of collecting the spectra, everything else is just manipulations in code.  Simple changes in the code shift the interface from having lots of things chosen for you to needing to make lots of choices.
## PiSpec20 Requirements  
The *master branch* only works on Python 3.x, a separate branch has the files for Python 2.7.  I wrote this on a Raspberry Pi 3b+.  For Windows or Mac you will need to make small changes to the code to deal with OS peculiarities.  You will need to possess a Stellarnet spectrometer.
### Libraries 
For Raspbian OS, the `apt-get` package manager is preferred to `pip` in most cases.  For other Linux types, the appropriate package manager (*e.g.*, yum for CentOS) will depend on your Linux distribution.   
For Windows and MacOS, one would typically use `pip` to install Python libraries.  Help with pip is available at https://packaging.python.org/tutorials/installing-packages/  
- pyusb 1.0.0a3  (Linux python 3 example:  `sudo pip3 install pyusb==1.0.0a3`)  this is version specific, so `pip` is appropriate  
- screen (if you want to hide the background processes)
- numpy  
- python-matplotlib  
- libraries usually automatically included in Python
  - json  
  - python-requests  
  - python-flask  
  - python-virtualenv  (if you want to run this in a virtual environment)
  - Tkinter  
### Files to install
- 99-local.rules  needs to be copied to '/etc/udev/rules.d/' or updated to include rules for StellarNet devices.  Otherwise 
you would need to run as root to get USB access.
- the rest of the files in PiSpec20_stellarnet should go into the same directory
- Issue `sudo chmod -x spectroweb.py` in the project directory if on a Linux system  
- on a Windows system you will need the free 'SWDrivers.zip' or 'SWDriver64.exe' from https://www.stellarnet.us/stellarnet-downloads  instead of the driver included in this package  
- use the 'run_hidden' bash script to start the project without showing the command line.  From the command line issue `sudo chmod +x run_hidden` to make the bash script executable.  On Windows a batch file would substitute the bash script.
### Other Hardware  
- a USB connected StellarNet spectrometer  
- a light source if you are going to do absorbance experiments
## How to Help  
I don't write in Python for a living, nor particularly do a lot of programming.  And it shows in the code.  
If you wish to contribute please contact me.
## License  
Apache License 2.0.  A Stellarnet module is included under the Apache License 2.0, so the whole thing is, too.
