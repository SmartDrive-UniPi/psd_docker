# PSD_Docker  <br>
## ROS2 Jazzy Jalisco + Gazebo Harmonic + Ubuntu 24.04 Noble

## How to build the image and start the container
1) Go inside the cloned folder
2) Create an image from the Dockerfile: `docker build -t psd_noble_jazzy .`
3) Run the container: `docker run -it --gpus all --user ubuntu --network=host --ipc=host -v $PWD/../psd_ws/:/home/ubuntu/psd_ws -v /tmp/.X11-unix:/tmp/.X11-unix:rw --env=DISPLAY -v /dev:/dev --device-cgroup-rule="c *:* rmw" --name psd_container psd_noble_jazzy`
4) **Achtung!** Once inside, only for the first time **go to deps/ folder and launch `bash first_launch_script.sh`**: this will setup everything for you and configure all the dependencies. 

## How to use it:
At every pc reboot you need to do  `docker start psd_container`
After that you can access the container with `docker exec -it psd_container /bin/bash`
***CTRL + D*** to exit the container`

## First run of the container:
To be sure that everything is setup well, check the README in the ***deps/*** folder


## TODO: FINISH THIS README
