---
title: Using Correct Quantities and Units
parent: Write
nav_order: 2
---

# How to Use Units and Quantities in Equations and Calculations

## Goals

Almost every equation you write, or calculation you carry out, will have an associated _unit_ related to a [physical constant]({{ site.baseurl }}/reference/si/constants.html) such as time, length, or frequency. Using units correctly conveys the essential meaning of your calculations, and so gives meaning to the numerical _quantity_ you give. Since the units are so important to many areas of science and engineering, you should follow the conventions outlined here convey this meaning with clarity and accuracy.

## Further Reading

Good sources of advice are

- [**The Metric System**](https://metricsystem.net). Covers the [fundamental units](https://metricsystem.net/si/base-units), [constants](https://metricsystem.net/si/defining-constants), [prefixes](https://metricsystem.net/prefixes/), and the most common [derived units](https://metricsystem.net/derived-units/special-names). There is also a useful [style guide](https://metricsystem.net/style-guide) which expands on the rules and principles given here.

## Using Units for Quantities in Calculations and Documentation

### General Principles

1. **Quantities are in _Italics_, Units are in Roman**. Quantities in definitions and equations must be in _italic_ (slanted) type: regardless of the surrounding text. Likewise the unit name _or_ the unit symbol must be in roman type: again regardless of the surrounding text.

    |       **Incorrect**{: .red}       |        **Correct**{: .green}        |
    |:---------------------------------:|:-----------------------------------:|
    | the measured voltage V was 2 mV … | the measured voltage _V_ was 2 mV … |
    |    _the resistance R is 20 Ω_     |     _the resistance R is 20_ Ω      |
    |    $$\text{V}_{max} = 10\; V$$    |     $$V_{max} = 10\; \text{V}$$     |

2. **Unit _Names_ are always in Lowercase**. Unless used in a title or at the start of a sentence, unit names should be in lowercase. Unit names should also always be in roman type, regardless of the surrounding typeface.

    |       **Incorrect**{: .red}       |       **Correct**{: .green}       |
    |:---------------------------------:|:---------------------------------:|
    | _… an output of twenty milliamps_ | _… an output of twenty_ milliamps |
    |  _the watt is the unit of power_  | _the_ watt _is the unit of power_ |

3. **Unit Names are Never Contracted**. Always spell out unit names in full: if you need to contract the name, use the symbol instead. Likewise, you should never contact a prefix if you are spelling out the unit name in full. Always be consistent.

    | **Incorrect**{: .red} | **Correct**{: .green} |
    |:---------------------:|:---------------------:|
    |       20 kiloW        |     20 kilowatts      |
    |        5 MOhms        |      5 megaohms       |
    |        5 MOhms        |         5 MΩ          |

4. **Unit _Symbols_ are Usually in Lowercase: Unless Derived from a Name**. Most of the common units in electrical and electronic engineering derive from names (usually the discoverer of the effect or principle). For example the ampere (A), volt (V), ohm (Ω) and watt (W). The main exceptions are units of lengths (m), mass (g), and volume. For volumes, it is acceptable to write the litre symbols either as 'l' or 'L' (although note the litre is [_not_ an SI unit]({{ site.baseurl }}/reference/si/units.html#derived-si-units)). A list of SI standard and derived units is [in the reference section]({{ site.baseurl }}/reference/si/units.html).

5. **Prefixes for Names and Symbols are in Powers of 10, and Never Mixed**. Use the [correct prefix]({{ site.baseurl }}/reference/si/prefixes.html) for Unit Names and Symbols, with the Correct Spelling and Case. Thus unit names must always have the prefixed spelled out in full, and unit symbols should use the correct prefix contraction and case. Don't mix prefix names and symbols, for instance it is always 'kg' or 'kilogram' for a mass, and never 'kilog'.

    Always express the associated quality in powers of 10: and ideally with the exponent divisible by three. For example '$$2 \times 10^{-3}\, \text{A}$$' not '$$20 \times 10^{-2}\, \text{A}$$'. This also applies to uncertainties, errors and other qualification you might make to the quantity.

    Using exponents which are divisible by three allows you to convert between SI prefixes. For instance you can also write '$$2 \times 10^{-3}\, \text{A}$$' as '$$2\, \text{mA}$$'. You may find some non-SI prefixes in common use: especially the prefix 'centi' ($$10^{-2}$$) and 'deci' ($$10^{-1}$$). However you should stick to SI prefixes wherever possible.

6. **Use a Space Between a Quantity and Unit -- Never Between a Prefix or Units**. For both unit names and symbols, always use a space between the quantity and the unit. If you are using LaTeX, sometimes a thin-space ('`$\,$`'), or a half-space ('`$\;$`'), looks better than a full space ('`$\ $`'). For example, the table below shows the different spacing options in LaTeX math. Documentation at Leeds Beckett tends towards the thin-space, but any space is acceptable

    |     **LaTeX**      |     **Result**     |
    |:------------------:|:------------------:|
    | `$20\ \text{mA}$`  | $$20\ \text{mA}$$  |
    | `$20\; \text{mA}$` | $$20\; \text{mA}$$ |
    | `$20\: \text{mA}$` | $$20\: \text{mA}$$ |
    | `$20\, \text{mA}$` | $$20\, \text{mA}$$ |

    However whether you are using a name or symbol, don't put a space between the prefix and the unit: or use a hyphen. Both the name (or symbol) and the prefix form a single unit.

    | **Incorrect**{: .red} | **Correct**{: .green} |
    |:---------------------:|:---------------------:|
    |    10 milli volts     |     10 millivolts     |
    |     20 milli-amps     |     20 milliamps      |
    |         2m A          |         20 mA         |

7. **Include Units For All Quantities**. Since you are expressing the _value_ of a quantity as both the numerical value of the quantity _and_ the unit, you must include both. For example, if the lengths used to calculate the volume, $$V$$, are in m, then you should express $$v$$ as follows

    |          **Incorrect**{: .red}           |                    **Correct**{: .green}                     |
    |:----------------------------------------:|:------------------------------------------------------------:|
    | $$v = 10 \times 10 \times 10\ \text{m}$$ | $$v = 10\ \text{m} \times 10\ \text{m} \times 10\ \text{m}$$ |

    This rule also applies to calculations, as quantities without a unit are ambiguous. For example, you should show the calculation of the following time quantity $$t$$ as

    |           **Incorrect**{: .red}            |                **Correct**{: .green}                 |
    |:------------------------------------------:|:----------------------------------------------------:|
    | $$t = 100 - 50\ \text{s} = 50 \ \text{s}$$ | $$t = 100\ \text{s} - 50\ \text{s} = 50 \ \text{s}$$ |

    To maintain clarity in your writing, also make sure that units are correctly used in ranges of values. Documents at Leeds Beckett also prefer the word 'to' instead of the en-dash ('–'), as the en-dash can resemble a minus sign: especially in expressions.

    |           **Incorrect**{: .red}            |                   **Correct**{: .green}                   |
    |:------------------------------------------:|:---------------------------------------------------------:|
    |      $$T = 10 - 20\ ^\circ\text{C}$$       | $$T = 10\ ^\circ\text{C}\ \text{to}\ 20\ ^\circ\text{C}$$ |
    | … observed spectra between 225 – 4000 nm … |      … observed spectra between 225 nm to 4000 nm …       |

8. **Include Units in Uncertainties**. As an extension of the previous rule, when you are quoting a quantity with an uncertainty or error, always show the correct unit in _both_ cases. Doing so allows you to correctly specify the prefix, and avoids ambiguity. For instance the last two examples in the table below read the incorrect '$$4\; \pm1\, \text{mA}$$' with an order of magnitude difference in the measured quantity. Correctly specifying the unit in both cases avoids the reader believing you mean '$$4\; \text{A}$$', instead of '$$4\; \text{mA}$$'!

    |   **Incorrect**{: .red}   |       **Correct**{: .green}        |
    |:-------------------------:|:----------------------------------:|
    | $$20\; \pm10\, \text{V}$$ | $$20\, \text{V} \pm10\, \text{V}$$ |
    | $$4\; \pm1\, \text{mA}$$  | $$4\; \text{A} \pm1\, \text{mA}$$  |
    | $$4\; \pm1\, \text{mA}$$  | $$4\; \text{mA} \pm1\, \text{mA}$$ |

### Unit and Quantity Calculations

1. **Quantities Have Exactly _One_ Unit**. Quantities for all calculations must result in exactly one unit: which may be the unit $$1$$ for ratios. For consistency, you should also apply this rule to time: however for non-technical writing, you may relax this rule.

    |                **Incorrect**{: .red}                |  **Correct**{: .green}   |
    |:---------------------------------------------------:|:------------------------:|
    | $$ l = 1\ \text{m}\ 47\ \text{cm}\ {8}\ \text{mm}$$ | $$ l = 1.478\ \text{m}$$ |
    |     $$t = 1\ \text{h}\ \text{30}\ \text{min}$$      |  $$t = 1.5\, \text{h}$$  |
    |     $$t = 1\ \text{h}\ \text{30}\ \text{min}$$      | $$t = 90\, \text{min}$$  |

2. **Qualification or Information Attaches to _Quantities_, Not _Units_**. Quantities often have upper or lower limits, for example the maximum voltage of a power supply. These limits apply to the _quantity_ --- the unit remains unaltered. Thus you _must_ show any qualification from a quantity calculation attaching to the quantity and _not_ the unit.

    |      **Incorrect**{: .red}       |    **Correct**{: .green}    |
    |:--------------------------------:|:---------------------------:|
    | $$ V = 10\ \text{V}_\text{max}$$ | $$ V_{max} = 10\ \text{V}$$ |
    |    $$t_s = 1.5\, \text{h}_s$$    |  $$t_s = 1.5\, \text{h}$$   |

3. **Use a Centred Dot ('·') or Space for Unit Multiplication**. Where you are forming the unit symbol for an expression by multiplication of the units, use a space or centred dot to separate the component symbols, and avoid ambiguity. For example, the unit $$\text{m} \cdot \text{s}^{-1}$$ refers to metres per second, whilst $$\text{ms}^{-1}$$ is the unit symbol for reciprocal millisecond.

    Some sources suggest omitting the dot or space if it does not cause confusion, for example the symbol for the kilowatt hour is often shortened to $$\text{kWh}$$. It is hard to second guess what 'confusion' means for your reader. So for consistency, _always_ follow this rule and write the symbol for the kilowatt hour as $$\text{kW}\ \text{h}$$.

    |         **Incorrect**{: .red}          |                **Correct**{: .green}                 |
    |:--------------------------------------:|:----------------------------------------------------:|
    | metre per second as $$\text{ms}^{-1}$$ | metre per second as $$\text{m} \cdot \text{s}^{-1}$$ |
    |    kilowatt hour as $$\text{kWh}$$     |      kilowatt hour  as $$\text{kW}\ \text{h}$$       |

4. **Use a Solidus ('/'), Horizontal Line, or Negative Exponents for Unit Division**. Where you are forming the unit symbol for an expression by division of the units, indicate that division in the resulting unit symbol. For example write symbol for the unit meter per second as $$\text{m}/\text{s}$$, $$\frac{\text{m}}{\text{s}}$$ or $$\text{m}\ \text{s}^{-1}$$.

    You will usually use the solidus or exponent form for figures, graphs and tables where space is frequently limited. However you should use the solidus form only _once_ in the same unit symbol. Therefore the exponent form is also particularly convenient for complex symbols: especially those which involve a mix of multiplication and division.

    |                     **Incorrect**{: .red}                     |                   **Correct**{: .green}                    |
    |:-------------------------------------------------------------:|:----------------------------------------------------------:|
    | metre per second per second as $$\text{m}/\text{s}/\text{s}$$ | metre per second per second as $$\text{m} / \text{s}^{2}$$ |
    | metre per second per second as $$\text{m}/\text{s}/\text{s}$$ | metre per second per second as $$\text{m}\ \text{s}^{-2}$$ |
