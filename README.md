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
