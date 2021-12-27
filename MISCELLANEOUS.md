
to activate the generation of `compile_commands.json` in the build directory add this to the `CMakeList.txt` :
`set(CMAKE_EXPORT_COMPILE_COMMANDS ON)`
then run the usual `mkdir build && cd build` and `cmake ..` and move said file to the root directory of your project.

if the package is inside the ros workspace it might be necessary to fetch the json file from the build directories of the catkin workspace after having compiled the package.
