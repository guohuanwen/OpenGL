# Learn OpenGL
This is a project template for CMake, you can use this project template to create Modern OpenGL apps with C++. 

## learnopengl doc
https://learnopengl-cn.github.io/

## How to use it

 - If you need, please download Glad https://glad.dav1d.de/, place into /thirdparty
 - From the terminal use these commands
	 - `brew install glfw`
     - `git clone https://github.com/shrainu/m1-cmake-opengl-template.git`
	 - `cd m1-cmake-opengl-template`
	 - `mkdir build`
	 - `cd build`
	 - `cmake ..`
	 - `cmake --build .`
	 - `./template`

## Using with Visual Studio Code

 In order to use this template with Visual Studio Code you'll these extensions
 - [C/C++](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools)
 - [CMake Tools](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cmake-tools)
 - [CMake](https://marketplace.visualstudio.com/items?itemName=twxs.cmake)
 
 After you install all the extensions and enable them close the vscode and project folder and open them again.

## FAQ

### My code doesn't works what should i do?

Make sure you followed all the steps correctly. If you're still having problems read my about this topic [here](https://shrainu.github.io/posts/openGLonM1mac.html). I explained how to use this in depth there.

### My code used to work but it doesn't now

Make sure that you include GLEW before GLFW, and before including GLEW you have this line `#define GLEW_STATIC`. If you already have that, and you're still having problems you can contact me from this e mail : **batuhanyigit1705@gmail.com**. Before contacting just make sure that you didn't make anything wrong in your code.
