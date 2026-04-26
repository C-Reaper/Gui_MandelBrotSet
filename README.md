## Overview
This project is a C-based GUI application that displays a Mandelbrot set. The application is designed to run on multiple platforms, including Linux, Windows, and the web through Emscripten.

## Features
- Displays the Mandelbrot set.
- Supports zooming in and out.
- Utilizes AVX2 instructions for performance optimization.
- Works on Linux, Windows, and WebAssembly (through Emscripten).

## Project Structure
The project structure is as follows:
```
<Project>/
├── build/              # .exe files produced by Main.c
├── src/                # Source code directory
│   ├── Main.c          # Entry point of the application
│   └── *.h             # Header files used by Main.c
├── Makefile.linux      # Linux Build configuration
├── Makefile.windows    # Windows Build configuration
├── Makefile.wine       # Wine Build configuration
└── Makefile.web        # Emscripten Build configuration
```

### Prerequisites
- C/C++ Compiler and Debugger (GCC, Clang)
- Make utility
- Standard development tools
- Libraries needed in specific projects (X11 for Linux)

## Build & Run

### For Linux:
To build the project on Linux, navigate to the project directory and run:
```bash
make -f Makefile.linux all
```
To run the application:
```bash
./build/Main
```

### For Windows:
To build the project on Windows, navigate to the project directory and run:
```bash
make -f Makefile.windows all
```
To run the application, execute `Main.exe` from the `build/` directory.

### For WebAssembly (Emscripten):
To build the project for WebAssembly, navigate to the project directory and run:
```bash
make -f Makefile.web all
```
This will generate an HTML file that can be opened in a web browser to view the application.

### Build Options
- `make -f Makefile.(os) all`: Builds the output.
- `make -f Makefile.(os) do`: Builds and runs the output.
- `make -f Makefile.(os) clean`: Removes build artifacts.