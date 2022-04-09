# Simulation of Positron Shower Leakage for the Muon g-2 Experiment at Fermilab.
The Muon g-2 experiment uses 24 calorimeters surrounding a circular storage ring. Each calorimeter is made up of a matrix of 9×6 segmented PbF<sub>2</sub> crystals (2.5×2.5×14 cm3) read by Silicon Photo Multipliers (SiPMs).
This GEANT4 simulation is to understand and quantify the leakage of the positron showers in the passage through these crystals and then add it back
to the observed energy.  The visualization of 10000 events passing through the center of a particular crystal is shown below:</br>
<img width="302" alt="Screen Shot 2022-04-09 at 2 36 41 PM" src="https://user-images.githubusercontent.com/27436642/162587356-e166492e-5feb-4a8d-af92-0d0cb867b38b.png">

We simulate how the radiation is lost in the passage through PbF<sub>2</sub> crystals. Leakage effects at boundaries between crystals can be larger than when the positron hits the center of a crystal. The positrons emanating from muons decaying a
t the magic momentum on the ideal orbit would have a different angular distribution compared to the off-track ones. Thus we expect a different rate in the 9×6 grid structure of our calorimeter. There could also be other effects due to beam oscillations etc. </br>
All this is quantified with simulations. 
## Energy spectrum of each crystal
The distribution of mean positron energy (left panel) and occupancy(right panel) for each crystal when the positron beam is incident on the center of crystal 22. Since the beam is incident on crystal 22 it gets maximum hits explaining the red color.
<img width="744" alt="Screen Shot 2022-04-09 at 2 50 49 PM" src="https://user-images.githubusercontent.com/27436642/162587807-93a9b4bc-aad2-4242-a56e-275873bf5b33.png">

For a deeper understanding the energy projections around crystal 22 is shown below:
<img width="562" alt="Screen Shot 2022-04-09 at 2 56 42 PM" src="https://user-images.githubusercontent.com/27436642/162587978-7bf08ceb-d139-4ceb-b403-2b92ff7f8785.png">

This study has reproduces the losses/leakages due to the positron energy, impinging point on the calorimeter face, and angle of
incidence. An example of the mean energy distribution as a function of impinging point on the calorimeter face i.e. beam position 
is shown for 3.1 GeV positron spectrum for crytal 22. This matches to a high precision with the simulation in the TDR. </br>
<img width="368" alt="Screen Shot 2022-04-09 at 3 25 27 PM" src="https://user-images.githubusercontent.com/27436642/162588869-38f2ef63-73e6-4a0a-bd49-cb266de92620.png">
The &chi;<sup>2</sup>/NDF indicates the goodness of fit and this simulation. 
### Instructions for running the code:
These are the instructions for installing GEANT4 in mac OSX:
<ol> <li> Download Geant4 source code.</li>
  <li> Configure the build using CMake <b>(CMake version 3.3+) and GCC 4.8.5+, clang 3.6+ </b></li>
  <ul> In mac OSX install <li> CMake using the Darwin64 dmg installerpackage<\li> <li> Qt4 or Qt5<\li> <li> X11<\li> 
   <li> Make & install </li> 
   <li> Configure environment to use Geant4 </li>
    <ul> Download and install Geant4:
      <li> https://geant4.web.cern.ch/geant4/</li>
    <li> Extract the file </br>
 $ cd Downloads</br>
$ tar -xzf geant4.10.04.p02.tar.gz</br>
 </li></ul> </ol>
  
  **Next Step: Setting up the environment:**</br>
  Assuming Desktop to be the path of installation (can be anything):</br>
  $ cd Desktop</br>
   $ mkdir Geant4 </br>
   $ cd Geant4</br>
    $ cd /home/user/Downloads</br>
$ cp -r geant4.10.04.p02 /home/user/Desktop/Geant4</br>

 **Next Step: Create the Build folder:**</br>
 $ cd /home/user/Desktop/Geant4 </br>$ ls</br>
$ mkdir geant4.10.04.p02-build</br>
$ cd geant4.10.04.p02-build</br>
 $ cmake -DCMAKE_INSTALL_PREFIX=/home/user/Desktop/ Geant4/geant4.10.04.p02-install -DGEANT4_INSTALL_DATA=ON  -DGEANT4_USE_OPENGL_X11=ON -DGEANT4_USE_QT=ON /home/user/Desktop/Geant4/geant4.10.04.p02</br>
 **Start the Geant4 installation:**</br>
  $ make -jN</br>
$ make install</br>
Make sure to source geant4.sh before each usage!</br>
