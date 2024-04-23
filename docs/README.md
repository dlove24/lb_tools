# Tools and Documentation for Electronics, Electrical and Robotics Engineering at Leeds Beckett University 

# Overview

This site builds the core documentation required by the tools repository using a Github action to publish to Github pages. Behind the scenes the core documentation using [Jekyll](https://jekyllrb.com), with a modified version of the [Just the Docs](https://github.com/just-the-docs/just-the-docs) theme (see below). 

# Just the Docs Modifications

## Colours and Themes

The core site colours are based on the [W3 RAL Colours](https://www.w3schools.com/colors/colors_ral.asp): as used in other engineering documentation. These colours can be found in the file '`_sass/custom/setup.scss`'.

For the _CSS_ implementing the theme, the core implementation lives at '`_sass/color_schemes/lbu.scss`'. As implied, this provides the '`lbu`' theme for Just the Docs in the '`_config.yml`' file.

## Custom Layouts

The main changes to the Just the Docs theme are intended to provide visual compatability with MyBeckett. Currently these changes are provided as includes for both Just the Docs and Jekyll: both in the '`_includes`' subdirectory.

* `_includes/icons/expand.html`: Changes the default arrow for sub-sections from an outline arrow-head to a filled triangle, patterned on MyBeckett. The core SVG for this is included at '`assets/icons/expand.svg`'.
* `_includes/components/lb_nav.html`: Uses the `lb-nav-list-expander` class (patterned on `nav-list-expander`), which allows a different link style to be applied to links in the sidebar. Also uses `lb-nav-list-link` (patterned on `nav-list-link`) for individual list items.
* `_includes/components/lb_site_nav.html`: Builds the core collections, and uses `lb-nav-list-expander` to style the documentation within each collection.
* `_includes/components/sidebar.html`: Forces a difference between link colours in the sidebar, and those on the main page. This allows the sidebar to use a dark theme background, but retain the standard colour for documentation links.