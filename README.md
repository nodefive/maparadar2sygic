# Maparadar to Sygic Converter

A Python 3 tool designed to convert Speed Camera and Photo Radar data from the IGO format to the Sygic `offlinespeedcams.dat` format.

## Features
- Converts IGO `SpeedCamText.txt` files to Sygic-compatible database files.
- Supports custom type mapping between IGO and Sygic categories.
- Optional Google Maps generation to visualize added points.
- Supports both KMH and MPH units.

## Usage
Ensure the script is executable and run it:
```bash
chmod +x maparadar2sygic
maparadar2sygic [options] [files...]
```

## Command Line Arguments

### Positional Arguments
- `files`: One or more source files (e.g., `SpeedCamText.txt`) or directories to scan for IGO log files.

### Options
- `-t, --type {igo}`: The input format type. Currently supports `igo` (default: `igo`).
- `-d, --dat DAT_FILE`: The name of the output Sygic DAT file (default: `offlinespeedcams.dat`).
- `-u, --unit {kmh, mph}`: Speed limit units to use in the output file (default: `kmh`).
- `-it, --igotypes KEY=VAL...`: Custom mapping between IGO camera types and Sygic types. 
  - Format: `IGO_TYPE=SYGIC_TYPE` (e.g., `1=1,2=6`).
  - Use commas or semicolons to separate multiple mappings.
- `--debug`: Enable verbose output for debugging conversion issues.
- `--map`: Automatically generate a Google Maps HTML file containing the newly added speed camera points (enabled by default).
- `--dat2map`: Generate a Google Maps HTML file using points already existing in the specified DAT file.

## Example
Convert a specific file and set the output name:
```bash
maparadar2sygic -d my_cameras.dat SpeedCamText.txt
```

## License

MIT License — Copyright (c) 2025 nodefive

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
