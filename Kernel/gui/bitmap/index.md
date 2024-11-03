---
title: Bitmap
layout: home
nav_order: 3
parent: "GUI"
---

# Bitmap

## `bitmap.c`

### `draw_bitmap`

Arguments:

| Argument | Position | Type                  |
| :------- | :------- | :-------------------- |
| position | 1        | [`Point`]()           |
| data     | 2        | `const uint8_t *data` |

How it works:
#### [Takes the input] --> [Fetches the [`file_header`](#bitmapfileheader) and [`info_header`](#bitmapinfoheader) from the data] --> [Checks the `file_header->bfType` to see if it is type `BM` (HEX: `4D42`), if not, it does nothing] --> [Calculates the row size and then gets the pixel data] --> [Draws every pixel using the `vbe_putpixel` function]

Limits of `draw_bitmap`:
- Does not support Alpha (Defaults to opaque)

Also subject to change (｡◕‿◕｡)

## `bitmap.h`

### `BITMAPFILEHEADER`
`file_header` is type `BITMAPFILEHEADER` which is defined here:
```c
typedef struct {
    uint16_t bfType;
    uint32_t bfSize;
    uint16_t bfReserved1;
    uint16_t bfReserved2;
    uint32_t bfOffBits;
} BITMAPFILEHEADER;
```

### `BITMAPINFOHEADER`
`file_header` is type `BITMAPFILEHEADER` which is defined here:
```c
typedef struct {
    uint32_t biSize;
    int32_t biWidth;
    int32_t biHeight;
    uint16_t biPlanes;
    uint16_t biBitCount;
    uint32_t biCompression;
    uint32_t biSizeImage;
    int32_t biXPelsPerMeter;
    int32_t biYPelsPerMeter;
    uint32_t biClrUsed;
    uint32_t biClrImportant;
} BITMAPINFOHEADER;
```