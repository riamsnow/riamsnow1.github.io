---
title: "Bike Phone Mount"
excerpt: "Durable, UV-resistant phone mount designed for 23-25mm handlebars."
header:
  teaser: assets/img/full-final-render.png
---
# Motivation
  * The motivation behind designing a phone bike mount using top-down modeling is rooted in enhancing the safety, convenience, and overall user experience for cyclists. Cyclists often rely on their smartphones for navigation, tracking fitness data, or staying connected while riding. 
  * A well-designed bike mount ensures that the phone is securely and ergonomically positioned, reducing distractions and the need to handle the device manually. 
  * By adopting a top-down modeling approach, I was able to prioritize factors like ease of installation, stability, and adaptability to various phone sizes, guaranteeing a user-centric solution that promotes safer cycling and a more enjoyable riding experience.

# CAD Model
<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH512d4QTec90decfa6ef55bd0e2e4874408?mode=embed" width="640" height="480" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

# Assembly
  * Press the long and short threads into the main body in whichever orientation works best for your device. *
  * Press the movable end of the ball-and-socket joint into the back of the main body. *
  * Slide the phone supports onto the long and short threads and secure your device with the positioning nuts.
  * Press the other end of the ball-and-socket into the bike mount. *
  * Secure the mount to your bicycle using the M5-30mm hex screws.
*(Note: Due to the limitations of FFF printing, a heat gun may be needed to soften materials prior to press-fitting them together)

# Installation
  * This phone mount can be attached to your bike with the use of two [M5-30mm hex screws.](https://www.mcmaster.com/products/screws/alloy-steel-socket-head-screws-8/length~30-0-mm/length~30-mm/?s=m5+screws)

# Parts List

|                 Component                 | Image |
|:-----------------------------------------:|:-----:|
|      Body (PETG)                            |   ![](/assets/img/body-render.png)        |
|      Long Thread  (PETG)                    |   ![](/assets/img/long-render.png)        |
|      Short Thread  (PETG)                   |   ![](/assets/img/short-render.png)       |
|      Positioning Nut  (PETG, Qty: 2)        |   ![](/assets/img/nut-render.png)         |
|      Phone Support (PETG, Qty: 2)           |   ![](/assets/img/constraint-render.png)  |
|      Ball & Socket Joint (PETG)             |   ![](/assets/img/ball-socket-render.png) |
|      Bike Mount (PETG)                      |   ![](/assets/img/mount-render.png)       |
|      M5 - 30mm Hex Screw (Qty: 2)           |   ![](/assets/img/m5-30.png)              |

# What is top-down modeling?
Top-down modeling is a systematic approach where the entire product or assembly is conceptualized as a whole before diving into the finer details. This method allows designers to establish the overall architecture, define relationships between components, and establish constraints and parameters that govern the entire assembly's behavior.

Key features of top-down modeling include:

  * Hierarchical Structure: Designers create a hierarchical structure or assembly tree that represents the various components and sub-assemblies of the product. This structure helps organize the design into manageable units.

  * Parametric Relationships: Top-down modeling relies heavily on parametric modeling techniques. Designers define parameters (such as dimensions, angles, and relationships) that control the behavior and appearance of components. This ensures that changes made at the top level cascade down to affect all related components.

  * Global Design Intent: Designers establish the global design intent, which defines the fundamental characteristics and functionality of the product. This intent guides the creation of individual components, ensuring that they align with the overall design vision.

  * Component Interactions: Top-down modeling emphasizes how components interact with each other within the assembly. Designers can define constraints, mates, and relationships between parts, ensuring they fit and function correctly when assembled.

  * Adaptability: Top-down modeling makes it easier to accommodate design changes or variations since modifications made at the top level automatically propagate to subordinate components, reducing the risk of errors and inconsistencies.

# Design Considerations
## Material Selection
In the prototyping phase of my project, I initially used PLA (Polylactic Acid) filament due to its affordability. PLA allowed me to quickly iterate and refine the design while keeping costs low. However, as I moved towards the production of the final product, I made the switch to PETG (Polyethylene Terephthalate Glycol) filament. The decision to switch materials was primarily driven by PETG's strength and UV resistance properties. These qualities were essential for ensuring the long-term durability and performance of the final product, especially if it would be exposed to outdoor conditions. PETG's ability to withstand UV radiation without degradation ensured that the product would maintain its integrity and appearance over time, making it the ideal choice for a robust and enduring end result.

## Component Design
Originally, I incorporated the long and short threads as part of the main body in my design. However, as I wanted to enhance the overall quality and functionality of the product, I opted for a press-fit design approach. This design change allowed me to print the threads vertically, which significantly improved the precision and quality of the threads themselves. This shift in design approach ultimately ensured that the threads provided a higher level of reliability and performance in the final product.

I decided to take a more creative approach for the ball and socket component, shifting to a print-in-place mechanism. This change brought an exciting challenge to the project as it had to be designed in such a way to allow the entire joint to be printed as one piece. This not only simplified assembly but also ensured that the parts moved smoothly right after printing, making the user experience more enjoyable and intuitive. 
![](/assets/img/socket-cross-section.PNG "Cross section of the ball and socket joint.")

My overall goal was to minimize the number of off-the-shelf parts, limiting myself to printed components. This decision added a touch of innovation and fun to the final product, highlighting the possibilities of 3D printing.

![](/assets/img/full-final-render.png)
