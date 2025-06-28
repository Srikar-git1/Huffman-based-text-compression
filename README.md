# Word-Level and Character-Level Huffman Compression

This project implements and compares static Huffman compression at two different symbolic granularities:
- **Character-level Huffman encoding**
- **Word-level Huffman encoding** 

## Project Structure

```
word-huffman-compression/
├── README.md
├── .gitignore
├── LICENSE
├── main.cpp                       # Reads input from file and compares both methods
├── main_encode.cpp               # Word-level encoder: input.txt → compressed.bin
├── main_decode.cpp               # Word-level decoder: compressed.bin → recovered.txt
├── include/
│   ├── huffman_word_compressor.hpp
│   ├── huffman_word_decompressor.hpp
│   ├── huffman_char_compressor.hpp
│   └── huffman_char_decompressor.hpp
├── src/
│   ├── huffman_word_compressor.cpp
│   ├── huffman_word_decompressor.cpp
│   ├── huffman_char_compressor.cpp
│   └── huffman_char_decompressor.cpp
└── input.txt                     # Example input file
```

## Build & Run

### Build All

```bash
g++ -Iinclude main.cpp src/*.cpp -o compare
g++ -Iinclude main_encode.cpp src/*.cpp -o encode
g++ -Iinclude main_decode.cpp src/*.cpp -o decode
```

### Input File

Ensure you have an `input.txt` file in the root directory. Example:

```
a friend in need is a friend indeed a friend in need is a friend indeed
```

### Compare Compression

```bash
./compare
```

### Compress and Save to Binary

```bash
./encode  # creates compressed.bin
```

### Decompress

```bash
./decode  # reads compressed.bin → recovered.txt
```

## Output Example

```
Input Text (from input.txt):
a friend in need ...

Word-Level Decoded:
a friend in need ...

Char-Level Decoded:
a friend in need ...

Compression Ratios:
Word-Level: 0.29
Char-Level: 0.44
```

## Features

- Huffman tree built on actual frequency
- Dictionary embedded in compressed file
- Padding tracked and removed
- Encodes to and from binary file

## License

MIT License
