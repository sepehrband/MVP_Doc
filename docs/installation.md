# Installation

### 1. Install Dependencies 
MVP requires [FSL 5 or higher](https://fsl.fmrib.ox.ac.uk), [FreeSurfer, 5.3 or higher](https://surfer.nmr.mgh.harvard.edu/fswiki/DownloadAndInstall) and [QIT](http://cabeen.io/qitwiki). 

To check the version of above softwares on your computer, try below lines:
	

	which fsl
	which qit
	which freeview


### 2. Install MVP
To install MVP on your syste, download the MVP repository and add it to your system path. To access the MVP repository, please contact [@sepehrband](https://github.com/sepehrband) and provide below information:  
- Name:  
- Email:  
- Organization:   

Once you received the MVP package, save it in your desired location and run:

	sh setpath.sh


or manually modify the source (e.g. `~/.bashrc`).


	MVPDIR=/Users/sepehrband/softwares/MVP
	PATH=${MVPDIR}/bin/:${PATH}
	export MVPDIR PATH


### 3. Testing MVP  
Test the installation using bellow command:
	 

	mvp.pvs.fsout.sh

which will generate below message:

```text
	ERROR! No options were passed
	Usage: 
	map.pvs.epc.sh -f STUDY_FOLDER -s SUBJECT_ID -t FRANGI_	THRESHOLD -v MAX_PVS_VOLUME -b BG_SEGMENTATION -o OUTPUT_	DIR_NAME 
	Default values: 
		-t FRANGI_THRESHOLD [defualt = 0.00002] 
		-v MAX_PVS_VOLUME [default = do nothing, remove PVS 	large than are larger than MAX_PVS_VOLUME voxels] 
		-b BG_SEGMENTATION [default = 1, set to 0 to skip 	basal ganglia PVS segmentation] 
		-o OUTPUT_DIR_NAME [e.g. pvs_seg, default = study_	folder/subject_id/pvs]
	
		
	Example: sh mvp.pvs.fsout.sh -f /my_projects/aging_	project -s sub-01 -t 0.00001 -o pvs
		
	This script assumes there is a folder inside sub-01 	called fsout, which hosts FreeSurfer outputs (lable, mri 	... folders). 
	For example: /my_projects/aging_project/sub-01/fsout/mri 	folder must exists!
```

### 4. Additional pipeline dependency 
Automated pipeline provided in MVP uses MATLAB for different purposes, including image enhancement, posprocessing and certain feature extractions. For the ease of use, add below line to your source file (e.g. `~/.bashrc`).

    export PATH=/Applications/MATLAB_R2019b.app/bin/:${PATH}

Change `MATLAB_R2019b` with your MATLAB version.