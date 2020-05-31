# Installation

### 1. Install Dependencies 
MVP requires [FSL 5 or higher](https://fsl.fmrib.ox.ac.uk), [FreeSurfer, 5.3 or higher](https://surfer.nmr.mgh.harvard.edu/fswiki/DownloadAndInstall) and [QIT](http://cabeen.io/qitwiki). 

To check the version of above softwares on your computer, try below lines:
	

	which fsl
	which qit
	which freeview


### 2. Install MVP
Download MVP repository and add it to your system path. The direct link is provide below. To download the MVP manually clone the repository from the [MVP](https://github.com/sepehrband/MVP) GitHub.


	git clone https://github.com/sepehrband/MVP.git
	sh setpath.sh


or manually modify the source (e.g. `~/.bashrc`).


	MVPDIR=/Users/sepehrband/softwares/MVP
	PATH=${MVPDIR}/bin/:${PATH}
	export MVPDIR PATH


### 3. Testing MVP  
Test the installation using bellow command:
	 

	mvp.pvs.fsout.sh

which will generate below message:

	ERROR! No options were passed
    	
	Usage: 
	mvp.pvs.fsout.sh -f STUDY_FOLDER -s SUBJECT_ID -t FRANGI_THRESHOLD -o OUTPUT_DIR_NAME 
    	
	Default values: 
		-t FRANGI_THRESHOLD [defualt = 0.00002] 
		-o OUTPUT_DIR_NAME [e.g. pvs_seg, default = study_folder/subject_id/pvs]
		
	Example: sh mvp.pvs.fsout.sh -f /my_projects/aging_project -s sub-01 -t 0.00001 -o pvs
		
	This script assumes there is a folder inside sub-01 called fsout, which hosts FreeSurfer outputs (lable, 	mri ... folders). 
	For example: /my_projects/aging_project/sub-01/fsout/mri folder must exists!


### 4. Additional pipeline dependency 
Automated pipeline provided in MVP uses MATLAB for different purposes, including image enhancement, posprocessing and certain feature extractions. For the ease of use, add below line to your source file (e.g. `~/.bashrc`).

    export PATH=/Applications/MATLAB_R2019b.app/bin/:${PATH}