## Compile the Go Program (statically linked by default and will default to using the architecture of your current system's CPU)
    go build hello.go

## Run the Compiled Program
    ./hello

## To verify the binary is statically linked
    ldd ./hello
    readelf -d ./hello
    
## To check if the executable is 32-bit or 64-bit, whether it is statically linked, specific details about the binary format and architecture
    file ./hello

## Compile into a 32-bit executable
    GOARCH=386 go build -o hello32 hello.go

## Run the Compiled Program
    ./hello32

## To check if the executable is 32-bit, whether it is statically linked, specific details about the binary format and architecture
    file ./hello32

## Compile into a 64-bit executable
    GOARCH=amd64 go build -o hello64 hello.go

## Compile into a Windows 64-bit executable
    GOOS=windows go build -o helloWin64.exe hello.go

## Compile into a Windows 32-bit executable
    GOOS=windows GOARCH=386 go build -o helloWin32.exe hello.go

## Compile a 64 bit executable (make the binary more portable as it doesn't rely on external shared libraries, by disabling CGO (C Go) support in the the Go build process. CGO enables Go packages to call C code, but it requires dynamic linking to C libraries. Disabling CGO (CGO_ENABLED=0) ensures that the resulting binary is statically linked, meaning it includes all necessary libraries and dependencies within the executable itself.)
    CGO_ENABLED=0 go build -o hello0 hello.go
