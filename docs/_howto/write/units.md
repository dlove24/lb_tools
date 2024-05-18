---
title: Correct Quantities and Units 
parent: Write
nav_order: 2
---

# How to Use Units and Quantities in Equations and Calculations

## Goals

Almost every equation you write, or calculation you carry out, will have an associated _unit_ related to a [physical constant](https://metricsystem.net/si/defining-constants) such as time, length, or frequency. Using units correctly conveys the essential meaning of your calculations, and so gives meaning to the numerical _quantity_ you give. Since the units are so important to many areas of science and engineering, you should follow the conventions outlined here convey this meaning with clarity and accuracy. 

## Further Reading

Good sources of advice are

- [**The Metric System**](https://metricsystem.net). Covers the [fundamental units](https://metricsystem.net/si/base-units), [constants](https://metricsystem.net/si/defining-constants), [prefixes](https://metricsystem.net/prefixes/), and the most common [derived units](https://metricsystem.net/derived-units/special-names). There is also a useful [style guide](https://metricsystem.net/style-guide) which expands on the rules and principles given here.

## Using Units for Quantities in Calculations and Documentation

### General Principles

1. **Unit _Names_ are always in Lowercase**. Unless used in a title or at the start of a sentence, unit names should be in lowercase. Unit names should also always be in roman type, regardless of the surrounding typeface.

    | **Incorrect**{: .red}             | **Correct**{: .green}             |
    |:---------------------------------:|:---------------------------------:|
    | _… an output of twenty milliamps_ | _… an output of twenty_ milliamps |
    | _the watt is the unit of power_   | _the_ watt _is the unit of power_ |

2. **Unit Names are Never Contracted**. Always spell out unit names in full: if you need to contract the name, use the symbol instead. Likewise, you should never contact a prefix if you are spelling out the unit name in full. Always be consistent. 

    | **Incorrect**{: .red}| **Correct**{: .green}     |
    |:--------------------:|:-------------------------:|
    | 20 kiloW             | 20 kilowatts              |
    | 5 MOhms              | 5 megaohms                |
    | 5 MOhms             | 5 MΩ                      |

3. **Unit _Symbols_ are Usually in Lowercase: Unless Derived from a Name**. Most of the common units in electrical and electronic engineering derive from names (usually the discoverer of the effect or principle). For example amps ('A'), volts ('V'), ohms ('') and watts ('W'). The main exceptions are units of lengths ('m'), mass ('g'), and volume. For volumes, it is acceptable to write the litre symbols either as 'l' or 'L'. 

4. **Prefixes for Names and Symbols are in Powers of 10, and Never Mixed**. Use the [Correct Prefix](https://metricsystem.net/prefixes) for Unit Names and Symbols, with the Correct Spelling and Case. Thus unit names must always have the prefixed spelled out in full, and unit symbols should use the correct prefix contraction and case. Don't mix prefix names and symbols, for instance it is always 'kg' or 'kilogram' for a mass, and never 'kilog'.

    Always express the associated quality in powers of 10: and ideally with the exponent divisible by three. For example '$$2 \times 10^{-3}\, \text{A}$$' not '$$20 \times 10^{-2}\, \text{A}$$'. This also applies to uncertainties, errors and other qualification you might make to the quantity.

    Using exponents which are divisible by three allows you to convert between SI prefixes. For instance you can also write '$$2 \times 10^{-3}\, \text{A}$$' as '$$2\, \text{mA}$$'. You may find some non-SI prefixes in common use: especially the prefix 'centi' ($$10^{-2}$$) and 'deci' ($$10^{-1}$$). However you should stick to SI prefixes wherever possible.

5. **Use a Space Between a Quantity and Unit -- Never Between a Prefix or Units**. For both unit names and symbols, always use a space between the quantity and the unit. If you are using LaTeX, sometimes a thin-space ('`$\,$`'), or a half-space ('`$\;$`'), looks better than a full space ('`$\ $`'). For example, the table below shows the different spacing options in LaTeX math. Documentation at Leeds Beckett tends towards the thin-space, but any space is acceptable

    | **LaTeX**            | **Result**                |
    |:--------------------:|:-------------------------:|
    | `$20\ \text{mA}$`    | $$20\ \text{mA}$$         |
    | `$20\; \text{mA}$`   | $$20\; \text{mA}$$        |
    | `$20\: \text{mA}$`   | $$20\: \text{mA}$$        |
    | `$20\, \text{mA}$`   | $$20\, \text{mA}$$        |

    However whether you are using a name or symbol, don't put a space between the prefix and the unit: or use a hyphen. Both the name (or symbol) and the prefix form a single unit.

    | **Incorrect**{: .red}| **Correct**{: .green}     |
    |:--------------------:|:-------------------------:|
    | 10 milli volts       | 10 millivolts             |
    | 20 milli-amps        | 20 milliamps              |
    | 2m A                 | 20 mA                     |

6. **Units Apply to Qualities and Uncertainties**. When you are quoting a quantity with an uncertainty or error, always show the correct unit in _both_ cases. Doing so allows you to correctly specify the prefix, and avoids ambiguity. For instance the last two examples in the table below read the incorrect '$$4\; \pm1\, \text{mA}$$' with an order of magnitude difference in the measured quantity. Correctly specifying the unit in both cases avoids the reader believing you mean '$$4\; \text{A}$$', instead of '$$4\; \text{mA}$$'!

    | **Incorrect**{: .red}     | **Correct**{: .green}              |
    |:-------------------------:|:----------------------------------:|
    | $$20\; \pm10\, \text{V}$$ | $$20\, \text{V} \pm10\, \text{V}$$ |
    | $$4\; \pm1\, \text{mA}$$ | $$4\; \text{A} \pm1\, \text{mA}$$ |
    | $$4\; \pm1\, \text{mA}$$ | $$4\; \text{mA} \pm1\, \text{mA}$$ |

### Rules

1.  **Distinguish Crossings and Junctions**. Use a heavy black dot to indicate a junction between wires, as in @fig:WireJunction. Crossed wires _without_ a junction _are not connected_ (as in @fig:WireCrossing).
     
2.  **Make Crossings Unambiguous**. Try to cross wires at a suitable distance from components, as shown in @fig:WireCrossing, to make your crossings clear. _Never_ cross and connect at the same time: either cross or connect at a single point.
   
3.  **Use Horizontal and Vertical Alignment**. PCBs can require you to make odd layouts, but your circuit diagram should show components either horizontally or vertically. This makes it much easier to label your components; and so easier for the reader to understand your diagram. Exceptions should always _enhance_ readability, for instance you should lay out Wheatstone bridges with the resistors at 45° angles for quick identification.
   
4.  **Show Polarity Where Needed**. When you lay your components, showing where polarity is important, for example in some capacitors. Remember that all polarity for diodes, transistors, capacitors, etc. should use _conventional_ current flow.
   
5.  **Names on the Outside, Functions on the Inside**. Pin numbers should be next to the IC they relate to, outside, and as close to the relevant wiring as possible. If you need to indicate the function of a pin, for example '`CLK`', those labels should go on the inside of the part.
   
6.  **Use Value and Type Annotations Where Needed**. Label all parts, and [give appropriate units](https://metricsystem.net/derived-units/special-names/). You should also prefer the conventional units where your drawing software permits, for instance '2.2 kΩ' rather than '2K2R', or '10 µF' instead of '10uF'. Use a space between the quantity and the unit: you can also use a half-space to visually group the quantity and unit, but still show these are part of the same label.

### Final Checks

1. **Group Parts and Sub-Units**. Part names and numbers should be next to your symbols, with any labels, types or values working together to form a distinct group. You may use dashed or solid lines to emphasise a sub-unit, or distinct area of the circuit (for example an sub-circuit at a higher or lower voltage).
   
2. **Make the 'Natural' Direction of Signals, Voltages, and Currents Clear**. Typically your signal inputs will be on the left-hand side of the drawing, and outputs on the right. Likewise supply voltages are usually at the top of your page, and negative rails or ground at the bottom of the page.

    If you need to vary this, make it clear which direction you are using. You will want to make sure the final drawing is consistent, so you give the reader a 'natural' order to work through your drawing.

3. **Check Crossing and Junction Points**. Make sure that junctions and crossings are clear and distinguished. Don't draw connections close to components, for instance, but give some space to illustrate the junction.

4. **Break Up Supply and Ground Rails as Needed**. It is sometimes easier to have multiple supply or ground points, with clear labels: rather than drawing everything back to a single rail. Breaking up supplies and ground rails can draw attention to particular features, for example drawing separate ground points where multiple IC's are present. Similarly where you are using multiple IC's with a common input voltage (such as for digital logic), it may be clearer to label the pin and supply input, rather than showing every connection.

5. **Label Key Signal Lines**. Logic diagrams will typically need input and output signals labelled, together with reset and clock lines. If it helps, add truth or state tables, waveforms, or timing diagrams to show the dynamic state of the circuit. Tables of parts or pin numbers might also be helpful: for instance showing the layout of key signals on an IC with multiple op-amps.

6. **Check and Label Connections Between Systems**. You should split large circuit diagrams into smaller sections; similarly you should draw common sub-units once. You might also be drawing a circuit which take an input, or gives and output, to another circuit beyond your immediate interest. In this case, label all inputs and outputs, using circles or rectangles to show the connection between systems. A reference table showing the relationship between the inputs (or outputs) and the labels you are using on the diagram might also be helpful.  
