## To Compile a Single Rust Source File
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
