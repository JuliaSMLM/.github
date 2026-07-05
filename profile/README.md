# JuliaSMLM

**Julia tools for single-molecule localization microscopy (SMLM).**

![Diffraction-limited vs single-molecule localization rendering of "JuliaSMLM"](https://juliasmlm.github.io/SMLMDocs.jl/dev/assets/juliasmlm_hero.png)

Composable, high-performance Julia packages spanning the full SMLM workflow —
simulation, localization, post-processing, rendering, and analysis. Packages share a
common data model ([SMLMData.jl](https://github.com/JuliaSMLM/SMLMData.jl)) and offer
automatic GPU acceleration with CPU fallback. All are registered in the Julia General
registry — install any with `Pkg.add("PackageName")`.

## Packages

| Package | Stage | What it does |
| --- | --- | --- |
| [SMLMAnalysis.jl](https://github.com/JuliaSMLM/SMLMAnalysis.jl) | Pipeline | End-to-end analysis from a single config: detection, fitting, filtering, frame connection, drift correction, and rendering, with provenance tracking. |
| [SMLMData.jl](https://github.com/JuliaSMLM/SMLMData.jl) | Core | Shared data types: emitters, cameras, SMLD containers. |
| [MicroscopePSFs.jl](https://github.com/JuliaSMLM/MicroscopePSFs.jl) | Core | 2D/3D point-spread-function models and pixel integration. |
| [SMLMSim.jl](https://github.com/JuliaSMLM/SMLMSim.jl) | Simulation | Blinking super-resolution data and diffusion/tracking dynamics. |
| [SMLMBoxer.jl](https://github.com/JuliaSMLM/SMLMBoxer.jl) | Localization | Particle detection / ROI extraction, GPU + sCMOS weighting. |
| [GaussMLE.jl](https://github.com/JuliaSMLM/GaussMLE.jl) | Localization | Fast maximum-likelihood Gaussian-PSF fitting, GPU-accelerated. |
| [SMLMFrameConnection.jl](https://github.com/JuliaSMLM/SMLMFrameConnection.jl) | Post-processing | Link multi-frame blinks into single, higher-precision localizations. |
| [SMLMBaGoL.jl](https://github.com/JuliaSMLM/SMLMBaGoL.jl) | Post-processing | Bayesian Grouping of Localizations (BaGoL): merge an emitter's repeated blinks into single emitters, reaching precision beyond raw localizations. |
| [SMLMDriftCorrection.jl](https://github.com/JuliaSMLM/SMLMDriftCorrection.jl) | Post-processing | Fiducial-free 2D/3D drift correction via entropy minimization. |
| [SMLMRender.jl](https://github.com/JuliaSMLM/SMLMRender.jl) | Rendering | Render localizations to images (histogram, Gaussian, outline). |
| [SMLMView.jl](https://github.com/JuliaSMLM/SMLMView.jl) | Rendering | Interactive N-dimensional microscopy viewer (WGLMakie). |
| [SMLMMetrics.jl](https://github.com/JuliaSMLM/SMLMMetrics.jl) | Analysis | Particle-tracking metrics (all 14 Chenouard measures). |
| [SMLMClustering.jl](https://github.com/JuliaSMLM/SMLMClustering.jl) | Analysis | Clustering and spatial statistics (DBSCAN, HDBSCAN, Voronoi). |
| [ModelContextProtocol.jl](https://github.com/JuliaSMLM/ModelContextProtocol.jl) | Tooling | Julia implementation of the Model Context Protocol (MCP). |

## Getting started

```julia
using Pkg
Pkg.add("SMLMAnalysis")                          # the full detection → rendering pipeline
Pkg.add(["SMLMData", "SMLMSim", "SMLMRender"])   # or individual building blocks
```

Per-package docs live at `https://JuliaSMLM.github.io/<Package>.jl/stable` (e.g.
[SMLMData](https://JuliaSMLM.github.io/SMLMData.jl/stable)). Ecosystem overview and
shared conventions (such as pixel indexing):
[JuliaSMLM.github.io/SMLMDocs.jl/dev](https://JuliaSMLM.github.io/SMLMDocs.jl/dev/).

Issues and pull requests are welcome on any repository — each is developed and
versioned independently through the Julia General registry.
