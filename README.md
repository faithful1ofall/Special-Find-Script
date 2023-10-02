# Special-Find-Script
It helps finds .c extension by replacing .o extensions

# File Copy Script Readme

This Bash script is designed to search for files with a specified extension (".o") in an initial search directory, change the extension to ".c", and copy them to a destination directory. The script also handles cases where the initial search directory and destination directory are specified as ".", ".." for current and parent directories, respectively.

## Usage

To use the script, follow the usage format below:

```bash
./script.sh initial_search_directory destination_directory file1.o file2.o file3.o ...
```

### Arguments:

- `initial_search_directory`: The directory where the script searches for files with the ".o" extension.
- `destination_directory`: The directory where the modified ".c" files will be copied to.
- `file1.o`, `file2.o`, `file3.o`, ...: The list of files you want to find, change their extension, and copy to the destination directory.

## Behavior

- The script first checks if the initial search directory and destination directory are provided as arguments. If not, it displays a usage message and exits.

- It handles `.` and `..` arguments for the current and parent directories in both the initial search and destination directories.

- For each specified file with the ".o" extension, the script:
  1. Changes the file extension from ".o" to ".c".
  2. Uses the `find` command to locate files with the ".c" extension within the initial search directory.
  3. Handles duplicate files by appending an incrementing number to their names (e.g., filename1.c, filename2.c, etc.).
  4. Copies the found files with the new ".c" extension to the destination directory.
  5. Provides informative messages indicating the copying process.

- If a specified file with the ".o" extension is not found in the initial search directory, the script displays an error message.

## Example Usage

### Case 1: Parent and Current Directories

```bash
./script.sh .. . file1.o file2.o
```

- The script will search for "file1.c" and "file2.c" in the parent directory, change their extension to ".c", and copy them to the current directory.

### Case 2: Specific Directories

```bash
./script.sh /path/to/search_directory /path/to/destination_directory file3.o file4.o
```

- The script will search for "file3.c" and "file4.c" in the `/path/to/search_directory`, change their extension to ".c", and copy them to `/path/to/destination_directory`.
