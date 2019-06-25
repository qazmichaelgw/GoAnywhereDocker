# GoAnywhereDocker
## Requirement
* Docker and Nvidia-docker(docker nvidia runtime) on the host: Check with [NVIDIA/nvidia-docker](https://github.com/NVIDIA/nvidia-docker)
* X11 Server install:

      $ apt-get install xauth xorg openbox

## Usage
- For the first time before runing up the docker, you should setup X11 socket and X11 auth files by runing command:
```
      XSOCK=/tmp/.X11-unix
      XAUTH=/tmp/.docker.xauth
      touch $XAUTH
      xauth nlist $DISPLAY | sed -e 's/^..../ffff/' | xauth -f $XAUTH nmerge -
```

- You should setup the envorionment variable of CODE_FOLDER and DATA_FOLDER to the absolute path in
  the host machine. 

```
export CODE_FOLDER=your_code_folder e.g. /home/gaowei/intention_net_journal
export DATA_FOLDER=your_data_folder e.g. /home/gaowei/NavCamp
```

- Run docker.run for the running environment.

- your code is under /mnt

- your data is under /data
