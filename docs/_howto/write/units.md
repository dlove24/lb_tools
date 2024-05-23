---
title: Correct Quantities and Units 
parent: Write
nav_order: 2
---

# How to Use Units and Quantities in Equations and Calculations

## Goals

Almost every equation you write, or calculation you carry out, will have an associated _unit_ related to a [physical constant](/reference/si/constants.html) such as time, length, or frequency. Using units correctly conveys the essential meaning of your calculations, and so gives meaning to the numerical _quantity_ you give. Since the units are so important to many areas of science and engineering, you should follow the conventions outlined here convey this meaning with clarity and accuracy. 

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

3. **Unit _Symbols_ are Usually in Lowercase: Unless Derived from a Name**. Most of the common units in electrical and electronic engineering derive from names (usually the discoverer of the effect or principle). For example the ampere ('A'), volt ('V'), ohm ('') and watt ('W'). The main exceptions are units of lengths ('m'), mass ('g'), and volume. For volumes, it is acceptable to write the litre symbols either as 'l' or 'L' (although note the litre is [_not_ an SI unit](/reference/si/units.html#derived-si-units)). 

4. **Prefixes for Names and Symbols are in Powers of 10, and Never Mixed**. Use the [correct prefix](/reference/si/prefixes.html) for Unit Names and Symbols, with the Correct Spelling and Case. Thus unit names must always have the prefixed spelled out in full, and unit symbols should use the correct prefix contraction and case. Don't mix prefix names and symbols, for instance it is always 'kg' or 'kilogram' for a mass, and never 'kilog'.

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
