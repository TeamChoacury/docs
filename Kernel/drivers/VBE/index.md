---
title: VBE
layout: home
nav_order: 1
parent: "Drivers"
---

# VBE documentation

Limits of the GPU:

| Name           | Limit          |
| :------------- | :------------- |
| Acceleration   | N/A            |
| Availability   | QEMU / BOCHS   |

## How the driver works
#### [Detected] --> [Initialize the BGA device]

## `vbe.c`

### Includes
Headers included in `vbe.c`

- `types.h`
- `../memory/kmalloc.h`

### Definitions
Definitions declared in `vbe.c`
- `#define ADDRESS 0xFD000000`¹
- `#define FONT_WIDTH 8`²
- `#define FONT_HEIGHT 16`²
Notes:
- ¹ This shouldn't be hardcoded, but in most QEMU versions this is where the LFB address is.
- ² Hardcoded for the PSF1 font


### Variables
Variables declared in `vbe.c`
```c
static int cursor_x = 0;
static int cursor_y = 0;
int VBE_WIDTH  = 1920;
int VBE_HEIGHT = 1080;
```

### Functions
Functions declared in `vbe.c`

List:
- `BgaSetVideoMode`
- `BgaSetBank`¹
- `vbe_putpixel`
- `vbe_fillrect`
- `vbe_fillrect`
- `vbe_getpixel`
- `vbe_drawline`
- `putchar`
- `print`
- `reset_cursor`
- `set_cursor`
- `BgaWriteRegister`¹
- `BgaReadRegister`¹
Notes:

 - ¹ Do not use these functions if you dont know what are you doing with the GPU!

Definitions:
```c
void BgaSetVideoMode(unsigned int Width, unsigned int Height, unsigned int BitDepth, int UseLinearFrameBuffer, int ClearVideoMemory);
void BgaSetBank(unsigned short BankNumber);
void vbe_putpixel(u32 x, u32 y, u32 color);
void vbe_fillrect(u32 sx, u32 sy, u32 ex, u32 ey, u32 color);

void vbe_clear_screen(u8 color);
void vbe_drawline(u32 x1, u32 y1, u32 x2, u32 y2, u8 color);
u32 vbe_getpixel(u32 x, u32 y);
void putchar(int x, int y, char c, PSF1_FONT* font, uint32_t color);
void print(const char* str, PSF1_FONT* font, uint32_t color);
void reset_cursor();
void set_cursor(int x, int y);
```

## `vbe.h`

### Definitions
Definitions declared in `vbe.h`
```c
#define VBE_DISPI_BANK_ADDRESS          0xA0000
#define VBE_DISPI_BANK_SIZE_KB          64

#define VBE_DISPI_MAX_XRES              1024
#define VBE_DISPI_MAX_YRES              768

#define VBE_DISPI_IOPORT_INDEX          0x01CE
#define VBE_DISPI_IOPORT_DATA           0x01CF

#define VBE_DISPI_INDEX_ID              0x0
#define VBE_DISPI_INDEX_XRES            0x1
#define VBE_DISPI_INDEX_YRES            0x2
#define VBE_DISPI_INDEX_BPP             0x3
#define VBE_DISPI_INDEX_ENABLE          0x4
#define VBE_DISPI_INDEX_BANK            0x5
#define VBE_DISPI_INDEX_VIRT_WIDTH      0x6
#define VBE_DISPI_INDEX_VIRT_HEIGHT     0x7
#define VBE_DISPI_INDEX_X_OFFSET        0x8
#define VBE_DISPI_INDEX_Y_OFFSET        0x9

#define VBE_DISPI_ID0                   0xB0C0
#define VBE_DISPI_ID1                   0xB0C1
#define VBE_DISPI_ID2                   0xB0C2
#define VBE_DISPI_ID3                   0xB0C3
#define VBE_DISPI_ID4                   0xB0C4

#define VBE_DISPI_DISABLED              0x00
#define VBE_DISPI_ENABLED               0x01
#define VBE_DISPI_VBE_ENABLED           0x40
#define VBE_DISPI_NOCLEARMEM            0x80

#define VBE_DISPI_LFB_PHYSICAL_ADDRESS  0xE0000000


#define VBE_DISPI_BPP_4   				0x04
#define VBE_DISPI_BPP_8   				0x08
#define VBE_DISPI_BPP_15  				0x0F
#define VBE_DISPI_BPP_16  				0x10
#define VBE_DISPI_BPP_24  				0x18
#define VBE_DISPI_BPP_32			    0x20
#define VBE_DISPI_LFB_ENABLED 			0x40

#define HD								1280,720
#define FHD 							1920,1080
#define UHD								3840,2160
```

### Structs
Structs defined in `vbe.h`
```c
typedef struct {
	unsigned char magic[2];
	unsigned char mode;
	unsigned char charsize;
} PSF1_HEADER;

typedef struct {
	PSF1_HEADER* psf1_Header;
	void* glyphBuffer;
} PSF1_FONT;

```


### Includes
Headers included in `vbe.h`
- `types.h`


