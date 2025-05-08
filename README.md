# Huffman Compression

This repository contains the implementation of a Huffman Compression algorithm using assembly for the 64-bit x86 architecture. The program supports both encoding and decoding functionalities for compressing and decompressing data based on character frequencies. The assembly code is structured with separate modules for encoding, decoding, frequency counting, tree construction, and system calls.

## Project Structure

```
httpsmojojojo-huffman-compression/
├── README.md          # This file
├── Makefile           # Makefile to build the project
└── src/
├── decode.asm     # Assembly code for decoding
├── encode.asm     # Assembly code for encoding
├── huffman.asm    # Main entry point and Huffman algorithm driver
├── syscalls.asm   # System call macros and wrapper functions
└── tree.asm       # Assembly code for building and handling Huffman tree
````

## Overview

This project implements Huffman compression in pure assembly, optimized for 64-bit systems. It performs the following steps:

1. **Frequency Counting**: Analyzes the input string to count the frequency of each unique character.
2. **Sorting**: Sorts characters by their frequency in descending order, using a custom sorting algorithm.
3. **Tree Construction**: Builds a binary Huffman tree based on character frequencies.
4. **Encoding**: Generates and returns a compressed representation of the input string.
5. **Decoding**: Decodes the compressed data back to the original string.

### Key Features

- **Memory Efficiency**: The program uses low-level memory allocation (`mmap`) to manage memory dynamically.
- **Custom System Calls**: Implements custom system calls for writing, memory mapping, and handling exit conditions.
- **Modular Design**: The project is structured in a modular fashion, with separate files for different components of the algorithm.

## Compilation & Usage

### Compilation

To compile the project, you can use the included `Makefile`:

```bash
make
````

This will compile the `huffman.asm` source file and produce the executable `huffman`.

### Usage

The program accepts two arguments:

1. **Action**: A character to specify the action (either encoding or decoding).

   * `e` for encoding
   * `d` for decoding
2. **Input**: The string to be encoded or decoded.

Example of encoding:

```bash
./huffman e "This is a test string for Huffman compression"
```

Example of decoding:

```bash
./huffman d "encoded_string"
```

### Error Handling

* If the program is called without the correct number of arguments, it will print an error message: `Insufficient arguments`.
* If the action is invalid, it will print an error message: `Invalid action`.

## Files Explanation

* `README.md`: Project documentation.
* `Makefile`: Instructions to build the project.
* `src/decode.asm`: Contains the decoding logic for the Huffman algorithm.
* `src/encode.asm`: Contains the encoding logic for the Huffman algorithm.
* `src/huffman.asm`: The main driver file, which checks the arguments and orchestrates the encoding or decoding process.
* `src/syscalls.asm`: Provides macros for common system calls, such as memory allocation and printing.
* `src/tree.asm`: Contains the logic for building and managing the Huffman tree.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
