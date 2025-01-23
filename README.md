# The Seaborn Plot That Looked Just Like The Others

A practical guide to creating consistent visualisations in Seaborn using the new `seaborn.objects` API. This notebook demonstrates how to maintain visual consistency across your data visualisations with minimal effort.

## Overview

This guide explores four key aspects of Seaborn plot customisation:
- **Context** - Size and scale presets for different presentation contexts
- **Style** - Background aesthetics and overall look & feel
- **Font** - Family selection and scaling options
- **Colour** - Understanding and effectively using different palette types

## Usage & Quick Start

Click <a href="https://colab.research.google.com/github/michellepace/seaborn-plot-consistency-guide/blob/main/Seaborn_Consistency_Guide.ipynb" target="_blank"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"></a>

Here's the core function for setting up consistent visualisations:

```python
import seaborn.objects as so
import seaborn as sns
from matplotlib.pyplot import cycler

def set_my_global_theme(
    style: str = "darkgrid",
    context: str = "notebook",
    font_scale: float = 1.0,
    font_family: str = "sans-serif",
    palette: str = "tab10"
) -> None:
    so.Plot.config.theme.reset()
    theme_settings = (
        sns.axes_style(style)
        | sns.plotting_context(context=context, font_scale=font_scale)
        | {
            "font.family": font_family,
            "axes.prop_cycle": cycler("color", sns.color_palette(palette))
          }
    )
    so.Plot.config.theme.update(theme_settings)
```

## Key Features

- Comprehensive guide to Seaborn's theme presets and colour systems
- Step-by-step examples with visual demonstrations
- Practical tips for choosing appropriate colour palettes
- Global theme setup function for consistent visualisations
- Built using the new `seaborn.objects` API

## Contents

1. **Context Settings**
   - Paper, Notebook, Talk, and Poster presets
   - Scale adjustments for different presentation contexts

2. **Style Presets**
   - Available options from decorated to minimal
   - Visual examples of each style

3. **Font Configuration**
   - Cross-platform compatible font families
   - Font scaling techniques

4. **Colour Systems**
   - Understanding categorical, sequential, and diverging palettes
   - Guidelines for choosing appropriate colour schemes
   - Examples of discrete steps vs. continuous gradients

5. **Practical Examples**
   - Real-world applications
   - Complete theme setup demonstration

## Licence

[License.md](License.md)
