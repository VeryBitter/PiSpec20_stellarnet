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
I wrote this on a Raspberry Pi 3b+.  For Windows or Mac you will need to make small changes to the code to deal with OS peculiarities.  You will need to possess a Stellarnet spectrometer.
### Libraries  
- pyusb 1.0.0a3  
- numpy  
- python-matplotlib  
- json  
- python-requests  
- curl  
- python-flask  
- python-virtualenv  
- Tkinter  
### Files to install
- /etc/udev/rules.d/99-local.rules  needs to be created or updated to include rules for StellarNet devices.  Otherwise 
you would need to run as root to get USB access.
### Other Hardware  
- a USB connected StellarNet spectrometer  
- a light source if you are going to do absorbance experiments
## How to Help  
I don't write in Python for a living, nor particularly do a lot of programming.  And it shows in the code.  This is 
also a work in progress.  
If you wish to contribute please contact me.
## License  
Apache License 2.0.  A Stellarnet module is included under the Apache License 2.0, so the whole thing is, too.
