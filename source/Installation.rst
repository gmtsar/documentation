.. index:: ! Installation

************
Installation       
************

Check out the GMTSAR github Wiki page:
 
https://github.com/gmtsar/gmtsar/wiki/GMTSAR-Wiki-Page

or read the installation information below

Installing GMTSAR with a Package Manager   
----------------------------------------

**Using Homebrew**

        To install necessary libraries and GMTSAR v6.2 with Homebrew follow these steps:
        (Check out homebrew at https://brew.sh/ )

 ::

        xcode-select --install
        brew tap dsandwell/homebrew-insar
        brew install wget
        brew install gmtsar         

Add GMTSAR to your path; for tcsh or csh:

 ::

      cd ~
      #
      #   edit your .tcshrc file and add the following lines
      #
      setenv GMTSAR /usr/local/GMTSAR
      setenv PATH $GMTSAR/bin:"$PATH" 

For bash:

 ::

      cd ~
      #  edit your .bashrc file and add the following lines
      export GMTSAR=/usr/local/GMTSAR
      export PATH=$GMTSAR/bin:"$PATH"

Now, test your installation by calling a GMTSAR command and checking the output.
It should print the usage of the command. For example, type "esarp" into the command
line and check it against the example below.

 ::

       % esarp
       esarp [GMTSAR] - Produce SAR processed image

       Usage: esarp filein.PRM fileout.SLC [R4]

Or try typing "phasediff":

 ::

       % phasediff
       phasediff [GMTSAR] - Compute phase difference of two images
       
       Usage: phasediff ref.PRM rep.PRM [-topo topo_ra.grd] [-model modelphase.grd]
       (topo_ra and model in GMT grd format

Installing manually via Package Manager and GitHub   
--------------------------------------------------

**Installing Libraries**

Install extra libraries. Note that depending on your OS version the
actual version numbers in some of the packages below may differ). The libraries 
below may require other libraries; use sudo apt[-get] install -y to automatically select yes

*Ubuntu 14.04 LTS*

 ::

       sudo apt-get install csh subversion autoconf libtiff5-dev libhdf5-dev wget
       sudo apt-get install liblapack-dev
       sudo apt-get install gfortran
       sudo apt-get install g++
       Install GMT from source since no GMT version >= 5 in 14.04.

*Ubuntu 16.06 LTS*

 ::

       sudo apt-get install csh subversion autoconf libtiff5-dev libhdf5-dev wget
       sudo apt-get install liblapack-dev
       sudo apt-get install gfortran
       sudo apt-get install g++
       sudo apt-get install libgmt-dev
       sudo apt-get install gmt-dcw gmt-gshhg (16.0 LTS)
       sudo apt-get install gmt

*Ubuntu 20.04 LTS or later*

 ::

       sudo apt install csh subversion autoconf libtiff5-dev libhdf5-dev wget
       sudo apt install liblapack-dev
       sudo apt install gfortran
       sudo apt install g++
       sudo apt install libgmt-dev
       sudo apt install gmt-dcw gmt-gshhg
       sudo apt install gmt

*CentOS 7*

 ::

       sudo yum install svn autoconf gcc-c++ libtiff-devel hdf5-devel wget
       sudo yum install gmt

*Fedora 23*

 ::

      sudo yum install csh subversion autoconf  gcc-c++ libtiff-devel hdf5-devel wget
      #(need fftw-developer for faster execution.)
      sudo yum install gmt


**Installing GMTSAR with GitHub**

 ::

      sudo -i
      cd /usr/local
      git clone --branch 6.2 https://github.com/gmtsar/gmtsar GMTSAR
      #   or
      #   checkout the master version for more new but not stable features. 
      git clone https://github.com/gmtsar/gmtsar GMTSAR
      #   or for UBUNTU 14, 16 where only gmt5 is available, use V5.8
      git clone --branch 5.8 https://github.com/gmtsar/gmtsar GMTSAR
      exit
      
      #  make youself the owner of this directory
      cd /usr/local
      sudo chown -R $USER GMTSAR
 
If you want to process ERS or Envisat Data, see how to install these orbit files below
and complete that step here. Then, compile and finish the install:

 :: 

      cd GMTSAR
      autoconf
      autoupdate
      ./configure --with-orbits-dir=/usr/local/orbits
      # For Ubuntu 21.04 or later, edit config.mk and add -z muldefs to your CFLAGS and LDFLAGS now
      make
      make install
 

Now, add GMTSAR to your path; for tcsh or csh:

 ::

      cd ~
      #
      #   edit your .tcshrc file and add the following lines
      #
      setenv GMTSAR /usr/local/GMTSAR
      setenv PATH $GMTSAR/bin:"$PATH" 

For bash:

 ::

      cd ~
      #  edit your .bashrc file and add the following lines
              export GMTSAR=/usr/local/GMTSAR
              export PATH=$GMTSAR/bin:"$PATH"

Now, test your installation by calling a GMTSAR command and checking the output.
It should print the usage of the command. For example, type "esarp" into the command
line and check it against the example below.

 ::

       % esarp
       esarp [GMTSAR] - Produce SAR processed image

       Usage: esarp filein.PRM fileout.SLC [R4]

Or try typing "phasediff":

 ::

       % phasediff
       phasediff [GMTSAR] - Compute phase difference of two images
       
       Usage: phasediff ref.PRM rep.PRM [-topo topo_ra.grd] [-model modelphase.grd]
       (topo_ra and model in GMT grd format


Installing an entire image on Ubuntu   
------------------------------------

**Virtual Machine**

For Windows users that have built in Ubuntu, you can run GMTSAR with a virtual machine. 
First:

Download VirtualBox or VMware, or any virtual machine that could load the .ova format (1.0).

Download the Ubuntu VM that has GMTSAR and all dependencies (including GMT) installed. http://topex.ucsd.edu/gmtsar/tar/Ubuntu20.0_GMTSAR6.1.ova

Load the VM into your VirtualBox or VMware, and start the system. The password is "gmtsar"

Open a terminal and type esarp, you should see the following message printing out.


 ::

       % esarp
       esarp [GMTSAR] - Produce SAR processed image

       Usage: esarp filein.PRM fileout.SLC [R4]


**Docker Image**

We are in the testing phase of providing a docker image for GMTSAR. Stay tuned.


Are you working with ERS or Envisat Data?
-----------------------------------------

To download orbit files for ERS or Envisat satellite data visit:

 ::

        http://topex.ucsd.edu/gmtsar/tar/ORBITS.tar

Then place them in /usr/local/ and untar them:
 
 ::

        sudo -i
        cd /usr/local
        mkdir orbits
        cd orbits
        tar -xvf ~/Downloads/ORBITS.tar # (need full path to ORBITS.tar)        



