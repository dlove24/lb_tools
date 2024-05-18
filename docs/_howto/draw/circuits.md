---
title: Circuit Diagrams
parent: Draw
nav_order: 2
---

# How to Draw Schematic Circuit Diagrams for Documentation

## Goals

This How To covers how you should approach the drawing of circuit diagrams for notes, reports and other documentation. Many simulation tools, PCB design, and other analysis tools also require a circuit diagram. However for these tools your goal is on the output of the tool itself. This How To, by contrast, focuses on how you should approach drawing a schematic circuit for documentation and communication purposes.

Good diagrams will also assist you in troubleshooting: and many of the [suggestions for troubleshooting](/trouble) also require clear diagrams. Drawing also reinforces your understanding of the circuit, again helping to make clear your intent to the reader (and building the foundational knowledge required to implement the diagram as required).

## Further Reading

Good sources of advice on drawing circuit diagrams can be found in

- Paul Horowitz and Winfield Hill (2020). _The Art of Electronics_, Third Edition. Cambridge University Press. Appendix E.
- Paul Scherz, Simon Monk (2016). _Practical Electronics for Inventors_, Fourth Edition. McGraw Hill. Chapter 7, Section 2.

## Drawing and Laying Out Components 

### General Principles

1. **Avoid Ambiguity**. You _should not_ include everything, but  you must provide all _critical_ information; for example, you may not label every pin on a DIP chip, but your readers will need to know where you put Pin 1 to locate the rest. You should also show any specific part numbers, polarities, orientation and other details that you require in your implementation.

2. **Use Space Appropriately**. Don't cram every possible feature into the smallest space possible: instead use space to help guide the reader. Equally don't use a whole page to layout a voltage divider. You aim is clarity, and the space is important to draw attention to features and show the critical aspects.
   
3. **Follow Conventions**. Use standard symbols, and layout the circuits (and sub-units) as you have seen in modules and on datasheets. These conventions help you (and your readers) to recognise common solutions to common problems. For instance, diagrams should show logic blocks with inputs on the left, and outputs on the right. Signals and signal lines, such as clock signals, should have labels with a standard name (for example '`CLK`'); and if needed provide a timing diagram for especially complex cases. 
   
4. **Follow One Standard**. The two main drawing standards are IEC and ANSI: pick **one** and use it consistently. You should draw circuits at Leeds Beckett using the IEC standards: the one exception is ANSI symbols for logic gates. Appropriate symbol libraries are [in the reference section](/symbols).
   
5. **Label Parts Consistently**. Choose the same prefix for all your parts, for example '`R`' for resistors; so '`R1`' and '`R2`' for instance. This helps you (and the reader) identify parts with ease.
   
6. **Use Colour Sparingly**. You should still draw circuit diagrams in black and white, and use colour only where meaning is essential. Most working diagrams require copying many times, and not always in colour. So you must make sure your meaning is clear, even if colour is not available.

### Rules

1.  **Distinguish Crossings and Junctions**. Use a heavy black dot to indicate a junction between wires, as in @fig:WireJunction. Crossed wires _without_ a junction _are not connected_ (as in @fig:WireCrossing).
     
2.  **Make Crossings Unambiguous**. Try to cross wires at a suitable distance from components, as shown in @fig:WireCrossing, to make your crossings clear. _Never_ cross and connect at the same time: either cross or connect at a single point.
   
3.  **Use Horizontal and Vertical Alignment**. PCBs can require you to make odd layouts, but your circuit diagram should show components either horizontally or vertically. This makes it much easier to label your components; and so easier for the reader to understand your diagram. Exceptions should always _enhance_ readability, for instance you should lay out Wheatstone bridges with the resistors at 45° angles for quick identification.
   
4.  **Show Polarity Where Needed**. When you lay your components, showing where polarity is important, for example in some capacitors. Remember that all polarity for diodes, transistors, capacitors, etc. should use _conventional_ current flow.
   
5.  **Names on the Outside, Functions on the Inside**. Pin numbers should be next to the IC they relate to, outside, and as close to the relevant wiring as possible. If you need to indicate the function of a pin, for example '`CLK`', those labels should go on the inside of the part.
   
6.  **Use Value and Type Annotations Where Needed**. Label all parts, and [give appropriate units](https://metricsystem.net/derived-units/special-names/). You should also prefer the conventional units where your drawing software permits, for instance '2.2 kΩ' rather than '2K2R', or '10 µF' instead of '10uF'. Use a space between the quantity and the unit: you can also use a half-space to visually group the quantity and unit, but still show these are part of the same label. The How To on  [SI units and quantities](/howto/write/units.html) covers the correct use of SI units at Leeds Beckett; follow this for all circuit diagrams where appropriate.

### Final Checks

1. **Group Parts and Sub-Units**. Part names and numbers should be next to your symbols, with any labels, types or values working together to form a distinct group. You may use dashed or solid lines to emphasise a sub-unit, or distinct area of the circuit (for example an sub-circuit at a higher or lower voltage).
   
2. **Make the 'Natural' Direction of Signals, Voltages, and Currents Clear**. Typically your signal inputs will be on the left-hand side of the drawing, and outputs on the right. Likewise supply voltages are usually at the top of your page, and negative rails or ground at the bottom of the page.

    If you need to vary this, make it clear which direction you are using. You will want to make sure the final drawing is consistent, so you give the reader a 'natural' order to work through your drawing.

3. **Check Crossing and Junction Points**. Make sure that junctions and crossings are clear and distinguished. Don't draw connections close to components, for instance, but give some space to illustrate the junction.

4. **Break Up Supply and Ground Rails as Needed**. It is sometimes easier to have multiple supply or ground points, with clear labels: rather than drawing everything back to a single rail. Breaking up supplies and ground rails can draw attention to particular features, for example drawing separate ground points where multiple IC's are present. Similarly where you are using multiple IC's with a common input voltage (such as for digital logic), it may be clearer to label the pin and supply input, rather than showing every connection.

5. **Label Key Signal Lines**. Logic diagrams will typically need input and output signals labelled, together with reset and clock lines. If it helps, add truth or state tables, waveforms, or timing diagrams to show the dynamic state of the circuit. Tables of parts or pin numbers might also be helpful: for instance showing the layout of key signals on an IC with multiple op-amps.

6. **Check and Label Connections Between Systems**. You should split large circuit diagrams into smaller sections; similarly you should draw common sub-units once. You might also be drawing a circuit which take an input, or gives and output, to another circuit beyond your immediate interest. In this case, label all inputs and outputs, using circles or rectangles to show the connection between systems. A reference table showing the relationship between the inputs (or outputs) and the labels you are using on the diagram might also be helpful.  
