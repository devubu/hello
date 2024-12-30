## Download Zig
    mkdir -p ~/Tools/zig
    mkdir -p ~/Tools/zig/v0.13.0
    curl -o ~/Tools/zig/v0.13.0/zig-linux-x86_64-0.13.0.tar.xz -L https://ziglang.org/download/0.13.0/zig-linux-x86_64-0.13.0.tar.xz
    curl -o ~/Tools/zig/v0.13.0/zig-windows-x86_64-0.13.0.zip -L https://ziglang.org/download/0.13.0/zig-windows-x86_64-0.13.0.zip

## Extract the archive
    cd ~/Tools/zig/v0.13.0
    tar -xf zig-linux-x86_64-0.13.0.tar.xz

## Export PATH for Zig
    export PATH=$PATH:$HOME/Tools/zig/v0.13.0/zig-linux-x86_64-0.13.0

## Compile the Zig Program (create executable from source or object files)
    zig build-exe hello.zig

## Run the Compiled Program
    ./hello

## To run a create executable and run immediately
    zig run hello.zig

## To initialize a `zig build` project in the current working directory
    zig init

## To build and run a Zig project in a single step
    zig build run

## To build and run unit tests defined in a Zig project
    zig build test

## To list available compilation targets
    zig targets

## To check if the binary is 32-bit or 64-bit, whether it is dynamically linked, specific details about the binary format and architecture
    file ./hello

## To verify the binary is dynamically linked (executable relies on external shared libraries (dynamically linked shared object libraries (denoted by the .so file extension)) to provide certain functions and resources at runtime)
    ldd ./hello
    readelf -d ./hello

## To compile a C Program
    zig cc hello.c -o hello

## To compile a C++ Program
    zig c++ hello.cpp -o hello

## Compile a C Program into a standalone (portable) 32-bit Linux binary (statically linked)
    zig cc hello.c -target x86-linux-musl -o hello

## Compile a C Program into a standalone (portable) 64-bit Linux binary (statically linked)
    zig cc hello.c -target x86_64-linux-musl -o hello

## To cross-compile a C Program into a standalone (portable) 32-bit Windows executable (x86 refers to the 32-bit architecture for Intel/AMD processors (specifically i386 or i686)
    zig cc hello.c -target x86-windows-gnu -o hello32.exe

## To cross-compile a C Program into a standalone (portable) 64-bit Windows executable (x86_64 refers to the 64-bit architecture for Intel/AMD processors (commonly referred to as AMD64 or x86-64)
    zig cc hello.c -target x86_64-windows-gnu -o hello64.exe

## To cross-compile a C Program for ARM aarch64 (64-bit ARM)
    zig cc hello.c -target aarch64-linux-gnu -o hello_aarch64

## Compile a C++ Program into a standalone (portable) 32-bit Linux binary (statically linked)
    zig c++ hello.cpp -target x86-linux-musl -o hello

## Compile a C++ Program into a standalone (portable) 64-bit Linux binary (statically linked)
    zig c++ hello.cpp -target x86_64-linux-musl -o hello

## To cross-compile a C++ Program into a standalone (portable) 32-bit Windows executable
    zig c++ hello.cpp -target x86-windows-gnu -o hello32.exe

## To cross-compile a C++ Program into a standalone (portable) 64-bit Windows executable
    zig c++ hello.cpp -target x86_64-windows-gnu -o hello64.exe

## To cross-compile a C++ Program for ARM aarch64 (64-bit ARM)
    zig c++ hello.cpp -target aarch64-linux-gnu -o hello_aarch64
