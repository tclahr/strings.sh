# strings.sh: A POSIX Shell Reimplementation of the 'strings' Command

A lightweight, portable, and POSIX-compliant shell script that extracts printable character sequences from any file. It serves as a simple, dependency-light alternative to the classic GNU/BSD `strings` utility, designed to run in minimal environments where `strings` may not be available.

## ✨ Key Features

- Highly Portable: Written in POSIX-compliant shell, ensuring it runs on a wide variety of Unix-like systems out of the box.

- Dependency-Light: Intelligently uses `tr`, `perl`, or `sed` for its core logic—tools that are available on almost any system.

- Standard `strings` Functionality: Emulates the core features of the standard strings command.

- Flexible Input: Reads from multiple files or standard input (`stdin`), making it perfect for use in command-line pipelines.

- Customizable String Length: Use the `-n` flag to specify the minimum character length to print.

- File Name Prefixing: Includes a `-f` option to print the source file's name before each string, just like the original.

- No Compilation Needed: As a shell script, there's no need for a compiler or build process. Just download and run.

## 🚀 Installation

1. Save the script as a file (e.g., strings.sh).

2. Make it executable:

```bash
chmod +x strings.sh
```

3. (Optional) Move it to a directory in your PATH for system-wide access:

```bash
sudo mv strings.sh /usr/local/bin/
```

## Usage

The command-line interface is designed to be familiar to users of the standard strings tool.

```text
Usage: strings.sh [OPTIONS] [FILE...]

Print the sequences of printable characters in files (stdin by default).
This is a shell implementation of the strings command.

OPTIONS:
  -f, --print-file-name   Print the name of the file before each string
  -n <number>             Set minimum string length (default: 4)
  -h, --help              Show this help message and exit

ARGUMENTS:
  FILE                    Input file path(s).
                          If no file is specified, reads from stdin.
```

### Examples

Extract strings from a binary file:

```bash
strings.sh /bin/ls
```

Process multiple files at once:

```bash
strings.sh file1.bin file2.bin
```

Read from stdin as part of a pipeline:

```bash
cat some_data.bin | strings.sh
```

Set a minimum string length of 8 characters:

```bash
strings.sh -n 8 /path/to/your/file
```

Print the filename before each extracted string:

```bash
strings.sh -f /bin/bash /bin/zsh
```

_Example Output:_

```bash
/bin/bash: /lib64/ld-linux-x86-64.so.2
/bin/bash: GCC: (GNU) 11.2.0
/bin/zsh: /lib64/ld-linux-x86-64.so.2
/bin/zsh: zsh
```

## 🤝 Contributing

Contributions are welcome! If you have ideas for improvements or find a bug, please feel free to open an issue or submit a pull request.

## 📜 License

This project is licensed under the Apache 2.0 License. See the LICENSE file for details.
