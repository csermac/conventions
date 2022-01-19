
to activate the generation of `compile_commands.json` in the build directory add this to the `CMakeList.txt` :
`set(CMAKE_EXPORT_COMPILE_COMMANDS ON)`
then run the usual `mkdir build && cd build` and `cmake ..` and move said file to the root directory of your project.

if the package is inside the ros workspace it might be necessary to fetch the json file from the build directories of the catkin workspace after having compiled the package.

$(package) not found during compilation of ros packages

```
find_package(Eigen3 REQUIRED)
include_directories(${EIGEN3_INCLUDE_DIR})
```


f-string formatting in python:
`rospy.loginfo(f"variable value: {variable}") `

## Docker 

build an image (correct taxonomy?) from the docker file "Dockerfile" in the current path "." and tag it as "tag_string"

`docker build . -f Dockerfile -t tag_string`

run a ros container build on top of nvidia ubuntu 18.04 image, with the same network as the host machine, the chosen container username (has to be created through the build by putting it in the Dockerfile), some environmental variables needed to set graphics correctly, some mapping between host and guest folder for correct working ( `/tmp/.X11-unix/` and `/tmp/.docker.xauth` might cause problems and need deletion or stuff).
Workdir is the internal workdir in the container, `--gpus all` is used to source the gpus and get them to work.
name is the one of the container and has to be unique, otherwise and error is printed.
after `--gpus all` the command is responsible for the image o use for the creation of the container, which is the name specified as `tag_string` in the build phase (the previous paragraph) with `:latest` appended.

`bash` is how to execute the command chosen for the launch.

```
docker run -it \     
    --network host \
    --user=csermac \
    --env="DISPLAY=$DISPLAY" \
    --env="QT_X11_NO_MITSHM=1" \
    -v /dev:/dev \
    --group-add=dialout \
    --group-add=video \
    --group-add=tty \
    --volume="/tmp/.X11-unix:/tmp/.X11-unix" \
    --volume="/etc/localtime:/etc/localtime:ro" \
    --volume="$HOME/prova_ros_shared_volume:/home/csermac/shared_volume:rw" \
    --volume="/tmp/.docker.xauth:/tmp/.docker.xauth" \
    -env="XAUTHORITY=/tmp/.docker.xauth" \
    --workdir="/home/csermac" \
    --name="ros_melodic_2" \
    --privileged \
    --gpus all \
    prova_ros:latest \
    bash -c "/bin/bash"
```
	
After exiting from a container it is supposedly stopped (at least it is when launched with bash command as entrypoint) so one can chekc the existance of such container by running
`docker container list --all` 
where `--all` includes th stopped ones, omitting it only showd the running ones.

A stopped container named "stopped_container" which as already been executed can be resumed by doing
`docker container start stopped_container` 
and then 
`docker container attach stopped_container`

To delete all the stopped containers the command is 
`docker container prune`
