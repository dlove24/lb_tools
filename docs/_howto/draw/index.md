---
title: Draw
nav_order: 1
has_children: true
---

# How To Draw Technical Diagrams for Notes and Documentation

Technical diagrams and drawing are a key tool in all fields of engineering, enabling you to accurately communicate complex ideas. All forms of technical drawing also have standards, some of which you can find in the [Reference section](). However many standards are also complemented by guidelines specific to the organisation you are working for: or working with. Thus the How To's in the section below cover both the universal and 'local' (Leeds Beckett) standards.

## General Principles

1. **Avoid Ambiguity**. You _should not_ include everything, but  you must provide all _critical_ information; for example, you may not label every pin on a DIP chip, but your readers will need to know where you put Pin 1 to locate the rest. You should also show any specific part numbers, polarities, orientation and other details that you require in your implementation.
2. **Use Space Appropriately**. Don't cram every possible feature into the smallest space possible: instead use space to help guide the reader. Equally don't use a whole page to layout a voltage divider. You aim is clarity, and the space is important to draw attention to features and show the critical aspects.
3. **Follow Conventions**. Use standard symbols, and layout the circuits (and sub-units) as you have seen in modules and on datasheets. These conventions help you (and your readers) to recognise common solutions to common problems. For instance, diagrams should show logic blocks with inputs on the left, and outputs on the right. Signals and signal lines, such as clock signals, should have labels with a standard name (for example '`CLK`'); and if needed provide a timing diagram for especially complex cases. 
4. **Follow One Standard**. The two main drawing standards are IEC and ANSI: pick **one** and use it consistently. You should draw circuits at Leeds Beckett using the IEC standards: the one exception is ANSI symbols for logic gates. Appropriate symbol libraries are [in the reference section](/symbols).
5. **Label Parts Consistently**. Choose the same prefix for all your parts, for example '`R`' for resistors; so '`R1`' and '`R2`' for instance. This helps you (and the reader) identify parts quickly.
6. **Use Colour Sparingly**. You should still draw circuit diagrams in black and white, and use colour only where meaning is essential. Most working diagrams require copying many times, and not always in colour. So you must make sure your meaning is clear, even if colour is not available.
