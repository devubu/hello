## Install package (A wrapper to use 'musl' as the C standard library for building applications)
    sudo apt install musl-tools

## Install musl toolchain for 32-bit architecture Linux
    rustup target add i686-unknown-linux-musl

## Install musl toolchain for 64-bit architecture Linux
    rustup target add x86_64-unknown-linux-musl

## To Compile a Single Rust Source File (dynamically linked by default)
    rustc example.rs

## Run the Compiled Program
    ./example

## To Create a New Package with Cargo
    cargo new hello --bin

## Compile the Rust Program (Puts the resulting binary in target/debug)
    cargo build

## Run the Compiled Program
    ./target/debug/hello

## Run and Compile in One Step
    cargo run

## To Compile your Rust Program with Optimizations Turned On (Puts the resulting binary in target/release)
    cargo build --release

## To Remove the 'target' Directory and it's Contents, Which Include the Compiled Release Binaries
    cargo clean

## Set up the project configuration (or modify it if it already exists) to specify the linker for the 32-bit musl target
    mkdir -p .cargo
    vim .cargo/config.toml
    [target.i686-unknown-linux-musl]
    linker = "musl-gcc"

## Compile into a standalone (portable) 32-bit Linux binary
    cargo build --target i686-unknown-linux-musl --release

## To check if the binary is 32-bit, whether it is statically linked, specific details about the binary format and architecture
    file ./target/i686-unknown-linux-musl/release/hello

## Set up the project configuration (or modify it if it already exists) to specify the linker for the 64-bit musl target
    mkdir -p .cargo
    vim .cargo/config.toml
    [target.x86_64-unknown-linux-musl]
    linker = "musl-gcc"

## Compile into a standalone (portable) 64-bit Linux binary
    cargo build --target x86_64-unknown-linux-musl --release

## To check if the binary is 64-bit, whether it is statically linked, specific details about the binary format and architecture
    file ./target/x86_64-unknown-linux-musl/release/hello

## To configure the project for cross-compilation (32-bit and 64-bit Linux binaries)
    mkdir -p .cargo
    vim .cargo/config.toml
    [target.x86_64-unknown-linux-musl]
    linker = "musl-gcc"
    
    [target.i686-unknown-linux-musl]
    linker = "musl-gcc"

## Compile into both 32-bit and 64-bit Linux binaries
    cargo build --target x86_64-unknown-linux-musl --release
    cargo build --target i686-unknown-linux-musl --release

## Install package (Provides the neccessary tools to compile Rust code into 32-bit (x86) and 64-bit (x64) Windows Executables on a Debian-based Linux system)
    sudo apt install -y mingw-w64

## Add the Windows 32-bit target (Alternatively, you could use x86_64-pc-windows-msvc for the Microsoft Visual C++ toolchain, but that generally requires a Windows host or Wine)
    rustup target add i686-pc-windows-gnu

## Set up the project configuration (or modify it if it already exists) to specify the linker for the 32-bit Windows target
    mkdir -p .cargo
    vim .cargo/config.toml
    [target.i686-pc-windows-gnu]
    linker = "i686-w64-mingw32-gcc"

## Compile into a 32-bit Windows executable
    cargo build --target i686-pc-windows-gnu --release

## Add the Windows 64-bit target
    rustup target add x86_64-pc-windows-gnu

## Set up the project configuration (or modify it if it already exists) to specify the linker for the 64-bit Windows target
    mkdir -p .cargo
    vim .cargo/config.toml
    [target.x86_64-pc-windows-gnu]
    linker = "x86_64-w64-mingw32-gcc"

## Compile into a 64-bit Windows executable
    cargo build --target x86_64-pc-windows-gnu --release

## To configure the project for cross-compilation (32-bit and 64-bit Windows executables)
    mkdir -p .cargo
    vim .cargo/config.toml
    [target.i686-pc-windows-gnu]
    linker = "i686-w64-mingw32-gcc"
    
    [target.x86_64-pc-windows-gnu]
    linker = "x86_64-w64-mingw32-gcc"

## Compile into both 32-bit and 64-bit Windows executables
    cargo build --target i686-pc-windows-gnu --release
    cargo build --target x86_64-pc-windows-gnu --release
