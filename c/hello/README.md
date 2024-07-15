## Install package
    sudo apt install -y gcc-multilib

## Compile the C Program
    gcc hello.c -o hello

## Run the Compiled Program
    ./hello

## To verify the binary is dynamically linked (executable relies on external shared libraries (dynamically linked shared object libraries (denoted by the .so file extension)) to provide certain functions and resources at runtime)
    ldd ./hello
    readelf -d ./hello
    
## To check if the executable is 32-bit or 64-bit, whether it is dynamically linked, specific details about the binary format and architecture
    file ./hello

## Compile into a standalone (portable) 32-bit executable
    gcc -m32 -static hello.c -o hello32

## To verify the 32-bit executable does not rely on external shared libraries (static libraries (denoted by the .a file extension))
    ldd ./hello32
    readelf -d ./hello32

## To check if the executable is 32-bit or 64-bit, whether it is statically linked, specific details about the binary format and architecture
    file ./hello32

## Run the 32-bit static executable
    ./hello32

## Compile into a standalone (portable) 64-bit executable
    gcc -m64 -static hello.c -o hello64
    
## To verify the 64-bit executable does not rely on external shared libraries (static libraries (denoted by the .a file extension))
    ldd ./hello64
    readelf -d ./hello64

## To check if the executable is 32-bit or 64-bit, whether it is statically linked, specific details about the binary format and architecture
    file ./hello64

## Run the 64-bit static executable
    ./hello64