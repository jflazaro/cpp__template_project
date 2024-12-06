Template for developing c++ projects 

The file structure was designed with CMake in mind.
Assign an executable name in the CMakeLists.txt by editing this line:
  set(MY_PROJECT_NAME "template_project") <-- Replace 'template_project' with your desired executable name.

Usage (MacOS/Linux):
cd build/
cmake ..
make

Usage (Windows):
cd build/
cmake ..
cmake -b .
(Find exe under build/Debug/)