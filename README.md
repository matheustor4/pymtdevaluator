# PyMTDEvaluator  

PyMTDEvaluator is a tool for evaluating the effectiveness of time-based Moving Target Defense (MTD) against availability attacks.

## Cite us

PyMTDEvaluator was first published in [2021 IEEE 32nd International Symposium on Software Reliability Engineering (ISSRE)](https://ieeexplore.ieee.org/abstract/document/9700355). If you use the tool, please cite the following publication.

	@inproceedings{torquato2021pymtdevaluator,
  	title={Pymtdevaluator: A tool for time-based moving target defense evaluation: Tool description paper},
  	author={Torquato, Matheus and Maciel, Paulo and Vieira, Marco},
  	booktitle={2021 IEEE 32nd International Symposium on Software Reliability Engineering (ISSRE)},
  	pages={357--366},
  	year={2021},
  	organization={IEEE}
	}



## Installation

PyMTDEvaluator depends on some libraries described in the paper. 

If you are a Docker container user, please follow the recommendations below.

PyMTDEvaluator docker container requires a XWindow server. 
- Xwindow server is usually available on most Linux OSes.
- For windows and mac, the user may select the preferred XWindow server. 

**Installation Linux-specific**

#Download PyMTDEvaluator-dockerImage.tar: Image available at: https://drive.google.com/file/d/10YIpgBKpakSDKULHjIOwSim88lS_Qwkd/view?usp=sharing

#Loading PyMTDEvaluator image on your Docker platform

	sudo docker load < PyMTDEvaluator-dockerImage.tar

#Checking images listing

	sudo docker images 

#Assign a tag to the downloaded image (replace <img-id> with the Image id)

	sudo docker tag <img-id> pymtdevaluator

#Jump to your Operating System:

#Starting xhost

	xhost +local:root

#Running docker container:
	
 	sudo docker run -it --rm     --env=DISPLAY     --env=QT_X11_NO_MITSHM=1     --volume=/tmp/.X11-unix:/tmp/.X11-unix:rw     pymtdevaluator

#Inside the container:
	cd /home/

	python3 PyMTDEvaluator.py

--NOTE

Remember that the generated files will be stored inside the container.
