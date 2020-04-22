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
  - name: Laio Oriel Seman
    affiliation: 3
  - name: Eduardo Augusto Bezerra
    affiliation: 1
affiliations:
 - name: Space Technology Research Laboratory (SpaceLab), Universidade Federal de Santa Catarina
   index: 1
 - name: Laboratory of Spacecraft Environment Interaction Engineering (LaSEINE), Kyushu Institute of Technology
   index: 2
 - name: Gradute Program in Applied Computer Science, Itajaí Valley University (UNIVALI)
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

# Centroid Determination

Considering that the input signal has a Gaussian behavior (pixels of stars), we propose the use of an IIR (infinite impulse response) filter to estimate the central coordinates of the centroids. For this purpose, it is possible to use a first-order filter (applied separately on each axis of the image) and with a gain that is constant and smaller than one, as presented in the following equations:

     X_{n} = [x_{n}, y_{n}] \\
     G_{n} = a^{n} \\
     Y_{n} = G_{n} \cdot X_{n} + (1 - G_{n}) \cdot Y_{n-1}

with:

    \left\{ \begin{array}{l}
        Y_{0} = X_{0} \\
        a = 0.8 \\
    \end{array}\right.

where:
    - $x$ is a pixel position in the x-axis;
    - $y$ is a pixel position in the y-axis;
    - $X$ is the measured value (x and y-axis coordinates);
    - $G_{n}$ is the weight of the current pixel;
    - $a$ is an optimal constant to minimize the centroid position error;
    - $Y_{n}$ is the estimation in the current iteration;
    - $Y_{n-1}$ is the estimation of the previous iteration.

To illustrate this process, we have matrix \eqref{eq:ex-single-star-matrix}, which represents a hypothetical image with a single star. Upon applying the previous equations to this matrix, after it goes through the threshold filter with a threshold equal to 150, we arrive at the results of \autoref{fig:kalman-values}. In this example, the system origin is the upper left corner, and the reading direction is from left to right, and from top to bottom.

# References
