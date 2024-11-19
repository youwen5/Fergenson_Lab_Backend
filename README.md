# WebSocketWithOpenCV Project

This project is a WebSocket server that uses Boost, OpenCV, and C++ to perform image processing. The server processes images, detects edges, and sends a confirmation message to the client upon completion. The project includes support for displaying processed images on the backend and can be configured to save output images instead.

## Prerequisites


## Installation

### With Nix

The preferred way to build this project is with the Nix package manager, which
builds in a hermetically sealed and reproducible build environment as well as
providing critical build dependencies. Nix will automatically manage the build
and orchestrate CMake and `make`.

Note that Nix is only supported on macOS and Linux. Windows users should use
first install the [Windows Subsystem for Linux
(WSL)](https://learn.microsoft.com/en-us/windows/wsl/install) and then follow
the below instructions.

1. Install Nix:

```bash
curl --proto '=https' --tlsv1.2 -sSf -L \
  https://install.determinate.systems/nix | sh -s -- install --determinate
```

> [!IMPORTANT]
> If you already have Nix installed and did not use the above installer, you
> must enable the experimental "flakes" and "nix-command" features.

2. Build the program
``` bash
nix build
```

3. Run the program
```bash
result/bin/WebSocketWithOpenCV
```

Alternatively, build and run it in one step with

```bash
nix run
```

### Janky way

Before setting up this project, ensure that the following libraries and tools
are installed on your system:

> [!NOTE]
> These are only required when compiling manually. When building with Nix, all
> dependencies are provided automatically.

- **CMake** (version 3.10 or higher)
- **Boost** (including Boost.Asio and Boost.Beast)
- **OpenCV** (version 4.0 or higher)
- **A C++ Compiler** (supporting C++17 or higher)
- **libtorch** (v2.5.0 or higher)

Using this approach, you will have to manually provide the dependencies above,
placing them somewhere that `CMake` can find them.

1. **Clone the Repository**
   ```bash
   git clone <repository-url>
   cd WebSocketWithOpenCV

2. **Make Build Directory**
mkdir build
cd build

3. **Change MakeList to update where your files are**
I recommend you to have a libs folder that includes the cloned version of boost and openCV.

You can specify the location to `libtorch` with the CMake flag

```
"-DCMAKE_PREFIX_PATH=<LIBTORCH_PATH_HERE>"
```

4. **CMake**
cmake --build .

5. **Make**
make
