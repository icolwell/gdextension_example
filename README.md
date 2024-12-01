# Example project that uses GDExtension.

This is adapted from the official example code: https://docs.godotengine.org/en/stable/tutorials/scripting/gdextension/gdextension_cpp_example.html
The purpose of this repo is to showcase the example code using both scons or cmake to build.

To build you would need:
- git (as godot-cpp is a git submodule)
- CMake
- A backend build system (e.g. Ninja)
- Compiler toolset (e.g. GCC)

# Using scons to build (as per tutorial)

```sh
cd godot-cpp
scons platform=linux custom_api_file=gdextension/extension_api.json
cd ..
scons platform=linux
```

Then open project in godot editor and run.

# Using cmake to build

```sh
cmake -B build
cmake --build build -j12
```

Edit the `demo/example.gdextension` to comment out the `scons` libs and instead use the `cmake` libs (semicolons act as comment lines).
Then open project in godot editor and run.
