---
title: RIM
layout: home
nav_order: 1
parent: "File Types"
---

# Choacury **R**aster **Im**age (**RIM**)
**RIM** is a custom Bitmap file type designed to work for ChoacuryOS, there are tools provided that allow you to easily convert between a normal Bitmap and a RIM.
It's similar to but not exactly a Bitmap, there are a few extra headers that make it easier for ChoacuryOS to work certain things out when drawing the image.
In addition to that, a standard Bitmap uses BGR, but RIM uses RGB (It makes more sense).
RIM by default supports RGBA.
So the channels look like this:

| Channel | Index |
|:-------:|:-----:|
| R       | 0     |
| G       | 1     |
| B       | 2     |
| A       | 3     |

**INSTEAD OF**:

| Channel | Index |
|:-------:|:-----:|
| B       | 0     |
| G       | 1     |
| R       | 2     |

Which is what it's like on normal Bitmaps

ChoacuryOS supports different image formats including, but not limited to:
- Bitmap
- RIM
- More to come later ʕᵔᴥᵔʔ