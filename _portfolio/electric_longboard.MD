---
title: "Electric Longboard"
excerpt: "Generative design SLS trucks + Large Format 3D printed deck = electric longboard"
header:
  image: assets/img/mini-board.jpeg
  teaser: assets/img/truck2.jpeg
gallery:
- image_path: assets/img/aluminum-assembly-render1.png
- image_path: assets/img/aluminum-assembly-render1.png
- image_path: assets/img/assembly-top-view.png
- image_path: assets/img/truck2.jpeg
- image_path: assets/img/full-assembly-2.png
- image_path: assets/img/longboard-scaled.jpeg
---
This is a fairly long writeup, so feel free to jump to any section that interests you!

[SLS Truck](#SLSTruck)\
[LF3DP](#lf3dp)


<a id="SLSTruck"></a>

# Generative Design & SLS Printing
# Motivation
Powder bed fusion (PBF) and generative design represent a powerful combination that has revolutionized manufacturing processes, particularly in the aerospace and automotive industries. This unique pairing combines cutting-edge technologies to enhance product design, optimize materials usage, and improve overall efficiency in the production of complex components. This combination offers several advantages, such as:
  * <strong>Lightweight Structures</strong>: Generative design enables the creation of lightweight structures that maintain structural integrity. In aerospace, this can lead to significant fuel savings, while in automotive applications, it contributes to improved fuel efficiency and overall performance.
  * <strong>Material Efficiency</strong>: The iterative nature of generative design allows for the creation of structures that use materials more efficiently. In aerospace, where weight is critical, this translates to reduced fuel consumption and increased payload capacity. In the automotive industry, it contributes to better energy efficiency and reduced environmental impact.
  * <strong>Complex Geometries</strong>: PBF's layer-by-layer construction and generative design's ability to create complex, organic shapes complement each other perfectly. This synergy is particularly beneficial in aerospace, where components often require intricate designs for optimal aerodynamics and structural performance.
  * <strong>Customization</strong>: Aerospace and automotive applications often require components tailored to specific requirements. The PBF-generative design duo allows for the creation of highly customized parts, optimizing performance for each application.
  * <strong>Reduced Waste</strong>: Traditional subtractive manufacturing processes can result in significant material wastage. PBF, in conjunction with generative design, minimizes waste by only using the necessary material to achieve optimal performance.


# Design
Fusion 360's Generative Design capabilities were used to iteratively create a longboard truck that could withstand the required forces. The generative design solver was run for both Nylon-12 and ALSi10Mg. 

To take advantage of Fusion 360's solver, preserve (green) and obstacle (red) geometries were designated. As explained by their names, preserve geometries should be kept by the solver, while obstacle geometries should be avoided. 
<img src="/assets/img/gen-des-geometries.png"/>
<figure-caption>Figure 1. Generative Design Setup.</figure-caption>


# CAD Models
## Nylon-12
<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH512d4QTec90decfa6e2ed67596e0e87df2?mode=embed" width="640" height="480" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

## ALSi10Mg
<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH512d4QTec90decfa6e251cf2898b16fefa?mode=embed" width="640" height="480" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

<a id="lf3dp"></a>

# Large Format 3D Printing
# Motivation
Large format 3D printing addresses the ever-growing demand for scaling up production capabilities and pushing the boundaries of traditional manufacturing. Motivated by the need to create more substantial and complex structures efficiently, this technology aims to overcome the limitations of smaller 3D printers. By enabling the fabrication of larger components in a single build, large format 3D printing enhances productivity, reduces assembly requirements, and opens up possibilities for producing life-sized prototypes, architectural elements, and even entire structural components. This innovation is driven by the desire to accelerate manufacturing processes, minimize material waste, and unlock new opportunities for industries ranging from construction to aerospace, where the ability to manufacture sizable parts in a cost-effective manner is priority.

# Design
Designing for Large Format 3D Printing (LF3DP) introduces unique challenges and considerations, primarily centered around the absence of supports for overhangs exceeding 45 degrees. As designers navigate this constraint, several key factors come into play to optimize the printing process and ensure successful outcomes.
  * <strong>Overhang Limitations</strong>: Given the absence of supports for steep overhangs, it is crucial to design with a keen awareness of the 45-degree threshold. Structures with angles surpassing this limit risk print distortions or failures. Designers must strategically incorporate geometries that adhere to this constraint to guarantee successful layer-by-layer deposition.
  * <strong>Layer Adhesion and Cooling</strong>:Optimizing layer adhesion becomes crucial, as large-format prints often involve extended print times. Ensuring proper cooling between layers helps prevent warping and maintains dimensional accuracy. Adjusting layer settings and incorporating features to enhance bonding between layers contribute to the overall stability of the print.
  * <strong>Structural Considerations</strong>: Considering the intended use of the printed object, designers should focus on optimizing its structural integrity. Reinforcing critical areas, redistributing loads, and incorporating appropriate features can enhance the overall strength of the final product, compensating for the limitations imposed by the absence of supports for steep overhangs.

As an added challenge, this design was also created through generative design. The setup was similar to the earlier one for PBF, with the additional use of a starting shape. Using generative design for the deck involved a lot of trial and error, highlighting one of the pitfalls associated with this technique. In the case of a simple geometry like this, it would have been faster to CAD by hand. However, the use of generative design made the load simulations significantly easier - more on this soon.
<img src="/assets/img/gen-des-deck.png"/>
<figure-caption>Figure 2. Generative Design Setup.</figure-caption>

The deck was designed for a 200lbs rider, with a safety factor of 2. This had to be achieved while also striving towards the objective of minimizing mass. Given these constraints, Fusion 360 designed the deck seen below. 
<img src="/assets/img/gen-des-deck-render.png"/>

When running the load simulation, it appears that Fusion 360 was able to generate a design given the contraints. The goal was to minimize mass, while also preventing a deflection of greater than 12 mm. Rather than enter the expected forces manually, Fusion 360 automatically transferred the forces from the generative design to the simulation. By iteratively decreasing the deck's thickness, both constraints were satisfied.
<img src="/assets/img/deck-simulation.png"/>

# CAD Model
<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH512d4QTec90decfa6ecebe828c0f80b296?mode=embed" width="640" height="480" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

{% include gallery %}


