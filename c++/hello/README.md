## Install package (Provides 32-bit libraries and support for compiling and linking 32-bit C++ programs on a 64-bit system)
    sudo apt install -y g++-multilib

## Compile the C++ Program
    g++ hello.cpp -o hello

## Run the Compiled Program
    ./hello

## To verify the binary is dynamically linked (executable relies on external shared libraries (dynamically linked shared object libraries (denoted by the .so file extension)) to provide certain functions and resources at runtime)
    ldd ./hello
    readelf -d ./hello

## To check if the binary is 32-bit or 64-bit, whether it is dynamically linked, specific details about the binary format and architecture
    file ./hello

## Compile into a standalone (portable) 32-bit Linux binary
    g++ -m32 -static hello.cpp -o hello32

## To verify the 32-bit binary does not rely on external shared libraries (static libraries (denoted by the .a file extension))
    ldd ./hello32
    readelf -d ./hello32

## To check if the binary is 32-bit or 64-bit, whether it is statically linked, specific details about the binary format and architecture
    file ./hello32

## Run the 32-bit static Linux binary
    ./hello32

## Compile into a standalone (portable) 64-bit Linux binary
    g++ -m64 -static hello.cpp -o hello64

## To verify the 64-bit Linux binary does not rely on external shared libraries (static libraries (denoted by the .a file extension))
    ldd ./hello64
    readelf -d ./hello64

## To check if the binary is 32-bit or 64-bit, whether it is statically linked, specific details about the binary format and architecture
    file ./hello64

## Run the 64-bit static Linux binary
    ./hello64

## Install package (Provides the neccessary tools to compile C and C++ code into 32-bit (x86) and 64-bit (x64) Windows Executables)
    sudo apt install -y mingw-w64

## Compile into a standalone (portable) 32-bit Windows executable
    i686-w64-mingw32-g++ -o hello32.exe hello.cpp -static

## Verify that the Windows executable is 32-bit
    file hello32.exe

## Compile into a standalone (portable) 64-bit Windows executable
    x86_64-w64-mingw32-g++ -o hello64.exe hello.cpp -static

## Verify that the Windows executable is 64-bit
    file hello64.exe
