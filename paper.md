---
title: 'CEST: A Centroid Extractor for Star Trackers'
tags:
  - C/C++
  - VHDL
  - Image Processing
  - Satellites
  - Star Trackers
authors:
  - name: Gabriel Mariano Marcelino
    orcid: 0000-0003-4889-6021
    affiliation: 1
  - name: Victor Hugo Schulz
    affiliation: 2
affiliations:
 - name: Space Technology Research Laboratory (SpaceLab), Universidade Federal de Santa Catarina
   index: 1
 - name: Laboratory of Spacecraft Environment Interaction Engineering (LaSEINE), Kyushu Institute of Technology
   index: 2
 - name: Applied Computer Science Master Program, Itajaí Valley University (UNIVALI)
   index: 3
date: 19 April 2020
bibliography: paper.bib

# Optional fields if submitting to a AAS journal too, see this blog post:
# https://blog.joss.theoj.org/2018/12/a-new-collaboration-with-aas-publishing
aas-doi: 10.3847/xxxxx
aas-journal: Astrophysical Journal
---

# Summary

The forces on stars, galaxies, and dark matter under external gravitational
fields lead to the dynamical evolution of structures in the universe. The orbits
of these bodies are therefore key to understanding the formation, history, and
future state of galaxies. The field of "galactic dynamics," which aims to model
the gravitating components of galaxies to study their structure and evolution,
is now well-established, commonly taught, and frequently used in astronomy.
Aside from toy problems and demonstrations, the majority of problems require
efficient numerical tools, many of which require the same base code (e.g., for
performing numerical orbit integration).
