---
title: "Microfluidic Device - WIP"
excerpt: "PDMS cast microfluidic device, made from SLA printed mold."
header:
  teaser: assets/img/ufluidic5.jpeg
gallery:
- image_path: assets/img/ufluidic1.jpeg
- image_path: assets/img/ufluidic3.jpeg
- image_path: assets/img/ufluidic5.jpeg
- image_path: assets/img/ufluidic-cast.jpeg
- image_path: assets/img/ufluidic-mold.jpeg
---
# Background
Microfluidic devices are small-scale systems capable of handling low volumes of fluids on the order of microliters to picoliters. They are often used in a variety of fields including chemistry, biology, and medicine. Applications of microfluidic devices include DNA analysis, cell sorting and manipulation, point-of-care diagnostics, and drug delivery systems. Their small size allows for faster analysis, lower costs, and the ability to perform multiple tests simultaneously.

# Design Considerations
Microfluidic devices typically exhibit laminar flows, posing a significant challenge for achieving thorough mixing since turbulent mixing is not feasible in these setups. Consequently, microfluidic homogeneous mixers heavily depend on diffusive mixing, which is intrinsically slower and requires elongated channels to attain adequate mixing. The objective of microfluidic mixing strategies is to optimize mixing efficiency by either reducing the time needed for satisfactory mixing or by minimizing the required channel length. Here we will examine two mixing strategies.

## Passive Mixing
Passive mixing strategies focus on improving mixing performance by prolonging the contact time between multiple species. Below are some common passive mixing strategies.
  * Lamination - including 90° rotation and/or wedge shaped inlets
  * Zigzag channels
  * 3-D Serpentine structures
  * Embedded barriers
  * Twisted channels
  * Surface-chemistry

## Active Mixing
Active mixing strategies enhance the efficiency of mixing by employing external forces on the sample flows to expedite the diffusion process. Below are some common active mixing strategies.
  * Acoustic / Ultrasonic
  * Dielectrophoretic
  * Electrokinetic time-pulsed
  * Pressure pertubation
  * Magnetic
  * Thermal
  * Electrohydrodynamic force
  * Magneto-hydrodynamic force
  * Electrokinetic instability


## Channel Design
This device relies on passive mixing schemes - specifically zigzag channels, embedded barriers, and 3-D geometry.

<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH512d4QTec90decfa6ea0939bd38a227bfe?mode=embed" width="640" height="480" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

# Manufacturing Considerations
Vat Photopolymerization (VPP) was chosen to manufacture molds due to its precision, but direct use of resin prints in finalized microfluidic devices was hindered by cytotoxicity and material instability. To address this, a two-step process involving VPP for mold creation and subsequent polydimethylsiloxane (PDMS) casting was employed. This two-step approach mitigates the challenges associated with direct resin use, allowing for the creation of biocompatible microfluidic platforms suitable for cell culture studies.

# Microdevice Fabrication
A series of steps were followed to get from the CAD model to the finalized microfluidic device. 
  * Convert STL file to g-code using Preform (Formlabs specific slicing software)
  * Print device on Formlabs Form 3 SLA printer
  * Wash completed print in isopropyl alcohol (IPA) until visibly clean
  * Cure device (with supports) using Formlabs UV cure following resin specific cure instructions
  * Coat device using Labcoter PDS 2010 parylene deposition machine (Specialty Coating Systems) according to manufacturer's instructions
  * Fill device with PDMS elastomer and curing agent mix at a weight ratio of 10:1.
  * Degas device in a vacuum chamber and cure with heat (80°C) for 3 hours.
  * Demold device and bond to glass coverslip with PlasmaFlo PDC-FMG plasma cleaner (Harrick Plasma)
  * Sterilize finalized device with an autoclave


{% include gallery %}

## Embedded YouTube video of the device working.
