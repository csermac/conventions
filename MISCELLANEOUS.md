
to activate the generation of `compile_commands.json` in the build directory add this to the `CMakeList.txt` :
`set(CMAKE_EXPORT_COMPILE_COMMANDS ON)`
then run the usual `mkdir build && cd build` and `cmake ..` and move said file to the root directory of your project.
