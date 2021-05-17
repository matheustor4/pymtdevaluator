PyMTDEvaluator depends on some libraries described in the paper. 

If you are a Docker container user, please follow the recommendations below.

PyMTDEvaluator docker container requires a XWindow server. 
- Xwindow server is usually available on most Linux OSes.
- For windows and mac, the user may select the preferred XWindow server. 

Installation Linux-specific

1) Download PyMTDEvaluator-dockerImage.tar: Image available at: https://drive.google.com/file/d/10YIpgBKpakSDKULHjIOwSim88lS_Qwkd/view?usp=sharing

2) Loading PyMTDEvaluator image on your Docker platform

sudo docker load < PyMTDEvaluator-dockerImage.tar

3) Checking images listing

sudo docker images 

4) Assign a tag to the downloaded image (replace <img-id> with the Image id)

sudo docker tag <img-id> pymtdevaluator

Jump to your Operating System:

#Starting xhost
$ xhost +local:root

#Running docker container:
$ sudo docker run -it --rm     --env=DISPLAY     --env=QT_X11_NO_MITSHM=1     --volume=/tmp/.X11-unix:/tmp/.X11-unix:rw     pymtdevaluator

# cd /home/

# python3 PyMTDEvaluator.py

--NOTE

Remember that the generated files will be stored inside the container.

