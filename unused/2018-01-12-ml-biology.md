---
layout: post
title: "CPSC 453a: Machine Learning for Biology"
date: 2018-01-12
---

### Lecture 1: Introduction to Single-Cell Data
1. Comparison to Bulk Data
  - Bulk data gives you the average of many cell responses together; averages can be deceiving. 
  - Single-cell data allows you to see the actual distribution.  
  - Results show that cell types are not precisely defined, even within single systems.
2. Single-Cell Proteomics: Mass Cytometry (CyTOF)  
   - CyTOF: Flow cytometry by time-of-flight of heavy metals in mass spectrometry.  
   - Steps: conduct experiment, preserve cellular state, permeabilize cells, label biomarkers with metal isotopes, cell by cell: vaporize biological material and run through MS machine.  
   - Advantages: targeted (by antibodies) and non-redundant. Avoids autofluorescence and spectral spillover from fluorescent tags (big problem with many tags).  
   - Each cell has a vector of intensity readouts for each isotope mass (length = number of isotopes).  
3. Single-Cell RNA-Seq  
    - Steps for Droplet Method:  
        - [1] Capture single-cells and barcoded beads in droplets, cell lysis + hybridization of cellular RNA to oligo-T on the beads.  
        - [2] Either cleave off primers and reverse transcribe in droplets, before breaking them (Klein) or break the droplets first, then reverse transcribe in bulk, before cleaving from bead (Macasko).  
        - [3] PCR amplification and sequencing.  
    - Problems: 
        - Differences in cell lysis (and other issues) create differences in RNA counts between cells.  
        - Drop-out: scRNA-seq has inefficient transcript capture (<5%), leading to
lots of gene columns with 0s.
        - The noise in number of transcripts is distributed as an overdispersed Poisson distribution (sample variance > sample mean, even though they should be equal)  
        - The negative binomial fits the data better; it has more parameters that allow variance > mean.
    - Advantages: high-dimensional, high-throughput, high resolution, heterogeneous, system-level view.
    
    
### Lecture	2: Dimensionality	Reduction
1. Data is often collected as a matrix of cells x genes (observations x variables)
2. Spectral Methods: take the eigenvectors of some matrix
    - Eigenvector: Mx = λx
        - Direction along which a matrix is invariant.
        - Vectors in that direction are only stretched.
    - Examples: 
        - Principle Components Analysis (PCA) uses covariance matrix
        - Multidimensional Scaling (MDS) uses double-centered distance matrix
5. Linear methods: can we re-express the data matrix in a different basis?
    - Take a few linear combinations of observed variables to capture max info.
    - Maximizing variation means minimizing redundancy = minimizing covariance.
    - Linear transformation: rotations and stretching.




