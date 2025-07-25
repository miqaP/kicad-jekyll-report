---
layout: home
title: Home
---

{% assign project = site.project %}
{% assign cacheBust = site.time | date:'?v=%s' %}
# {{ project.title }} v{{ project.version }}
![Main Render]({{ "/images/" | append: project.name | append: "-3d_top_angled.png" | absolute_url | append: cacheBust }}){: width="400" }

{{ project.description }}

[GitHub link]({{ project.repository }})

## Table of Contents
{% for section in project.sections %}
- [{{ section.title }}](#{{ section.anchor }})
{% endfor %}

{% for render in project.renders %}
### {{ render.title }}
![{{ render.title }}]({{ "/images/" | append: project.name | append: render.image_suffix | absolute_url | append: cacheBust }})
{% endfor %}

### Schematic
{% for variant in project.schematic_variants %}
- [{{ variant.name }} PDF]({{ "/documents/" | append: project.name | append: variant.file_suffix | absolute_url | append: cacheBust }})
{% endfor %}

### Layout
{% for variant in project.assembly_variants %}
- [{{ variant.name }} PDF]({{ "/documents/" | append: project.name | append: variant.file_suffix | absolute_url | append: cacheBust }})
{% endfor %}

### Interactive BOM
[IBOM HTML]({{ "/export/" | append: project.name | append: "-ibom.html" | absolute_url | append: cacheBust }})

### BOM
[BOM HTML]({{ "/export/" | append: project.name | append: "-bom.html" | absolute_url | append: cacheBust }})


### KiCad Revision Inspector (KiRI)

KiCad Revision Inspector (KiRI) is a tool for comparing different versions of KiCad projects. It exports project revisions to SVG format for visual comparison using an onion skin view. This helps identify changes and errors in PCB designs.

#### Light

- [KiRi Light]({{ "/kiri-light/index.html" | absolute_url | append: cacheBust }})

#### Dark

- [KiRi Dark]({{ "/kiri-dark/index.html" | absolute_url | append: cacheBust }})



### Downloads
{% for manufacturer in project.manufacturers %}
{% assign manufacturer_lc = manufacturer | downcase %}
#### {{ manufacturer }}
- [BOM/CPL ZIP]({{ "export/" | append: project.name | append: "-" | append: manufacturer_lc | append: ".zip" | absolute_url | append: cacheBust }})
- [BOM CSV]({{ "export/" | append: project.name | append: "-bom_" | append: manufacturer_lc | append: ".csv" | absolute_url | append: cacheBust }})
- [CPL CSV]({{ "export/" | append: project.name | append: "-cpl_" | append: manufacturer_lc | append: ".csv" | absolute_url | append: cacheBust }})
{% endfor %}

#### 3D Step
- [STEP File]({{ "/" | append: project.name | append: "-3d.step" | absolute_url | append: cacheBust }})

## Reports
{% include_relative erc_validation.md %}
{% include_relative drc_validation.md %}
{% include_relative report.md %}

{% if project.known_issues %}
## Known Issues
{{ project.known_issues | markdownify }}
{% endif %}

## Credits
{{ project.credits | markdownify }}