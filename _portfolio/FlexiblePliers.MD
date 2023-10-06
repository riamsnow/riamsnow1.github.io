---
title: "Multi-material Flexible Pliers"
excerpt: "Print in place flexible pliers, made with PLA & TPU"
header:
  teaser: assets/img/fp-full-image.png
---
# Motivation
The goal of this project was to design print-in-place flexible pliers. Print-in-place refers to the technique of 3D printing an object in a single piece, including all of its moving or functional parts, without the need for assembly after printing. Toys, puzzles, mechanical gadgets, and practical objects are just a few areas where print-in-place designs can be found.
There are several materials to be used for print-in-place designs. The most important thing to consider is how well the materials will adhere to each other. 

Below is a table of common filaments and how well they bond together:

|                 Materials                 | Relationship |
|:-----------------------------------------:|:-----:|
|      PLA + PETG      |   PLA will stick to PETG, but the bond between the two layers will be quite weak. This is sufficient for aesthetic prints but not recommended for mechanical parts.   |
|      PLA + ABS    |   PLA and ABD bond exceptionally well, even if subjected to strong mechanical stress. Be concious of warping between layers. |
|      PLA + TPU          |   PLA will bond with TPU without too many issues, but the bond won't be very strong. PLA is typically used as a support material for TPU prints as it is easier to remove.     |
|      ABS + PETG       |   ABS will stick to PETG with ease. However, the bond will be somewhat weak. This isn't great for mechanical projects but PETG could be printed as a support material for ABS.     |
|      TPU + PETG    |  TPU and PETG will form a moderately strong bond. They will only seperate under strong mechanical stress.    |


# CAD Model
<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH512d4QTec90decfa6ed35aa60b7838f7ce?mode=embed" width="640" height="480" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

# Design Considerations
The flexible core of this design went through several iterations. Originally a 4x4 grid of squares was used, but the multiple walls reduced flexibility. The final iteration consists of a 2x2 grid of larger squares to minimize the number of walls. 
Additionally, a dovetail joint was used to attach the PLA components to the TPU core. See the cross-section below. 
<img src = "/assets/img/fp-cross-section.png" alt = "Cross section of pliers" style = "height:256px; width:256px">


# Relevant specifications of the pliers (jaw length, jaw capacity) o Print settings
# Picture gallery of iterations and pliers.
# GIF of pliers working





# 3D Printed Parts

|                 Component                 | Image |
|:-----------------------------------------:|:-----:|
|      Left Handle (PLA)       |   ![](/assets/img/fp-handle-1.png)   |
|      Right Handle (PLA)      |   ![](/assets/img/fp-handle-2.png)   |
|      Left Jaw (PLA)          |   ![](/assets/img/fp-jaws-1.png)     |
|      Right Jaw  (PLA)        |   ![](/assets/img/fp-jaws-2.png)     |
|      Flexible Core (TPU)     |   ![](/assets/img/fp-core-1.png)     |



