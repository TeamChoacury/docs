---
title: RIMTils
layout: home
nav_order: 3
---

# RIMTils
Choacury **R**aster **Im**age Utilities.
This was made to make it easier to do things with RIM files, it has different modes that allow you to do different things, including converting between a standard Bitmap and a RIM. Here are the available modes:

| Mode                | Description                              |
| :------------------ | :--------------------------------------- |
| [convert](#convert) | Converts between Bitmap and RIM          |
| [resize](#resize)   | Resizes an image                         |
| [new](#new)         | Creates a blank RIM file                 |
| [info](#info)       | Fetches the information about a RIM file |

## Modes

### Convert
The convert utility allows you to convert between Bitmap and RIM.
Here are the available arguments:

| Argument       | Meaning                                                  |
| :------------- | :------------------------------------------------------- |
| `-m`, `--mode` | The mode (Can be either `ToBMP` or `ToRIM`)              |
| `-f`, `--from` | The path to the starting image                           |
| `-t`, `--to`   | The path where RIMTils will write the converted image to |

All of the above arguments are **required** for you to be able to use the utility.

Example usage:

- `RIMTils convert -m ToBMP -f "/test.rim" -t "/test.bmp"`
- `RIMTils convert --mode ToBMP --from "/test.rim" --to "/test.bmp"`
- `RIMTils convert -m ToRIM -f "/test.bmp" -t "/test.rim"`
- `RIMTils convert --mode ToRIM --from "/test.bmp" --to "/test.rim"`

### Resize
Not yet implemented.

### New
Not yet implemented.

### Info
Not yet implemented.