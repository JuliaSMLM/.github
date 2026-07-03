# JuliaSMLM

**Julia tools for single-molecule localization microscopy (SMLM).**

![Diffraction-limited vs single-molecule localization rendering of "JuliaSMLM"](https://juliasmlm.github.io/SMLMDocs.jl/dev/assets/juliasmlm_hero.png)

JuliaSMLM is a collection of composable, high-performance Julia packages covering
the full SMLM workflow — from simulating raw camera data, through localization and
post-processing, to rendering and quantitative analysis. Packages share a common
data model ([SMLMData.jl](https://github.com/JuliaSMLM/SMLMData.jl)) so they snap
together into pipelines, and performance-critical steps offer automatic GPU
acceleration with CPU fallback.

## Packages

All packages below are registered in the Julia General registry — install any of
them with `using Pkg; Pkg.add("PackageName")`.

### Core

| Package | Description |
| --- | --- |
| [SMLMData.jl](https://github.com/JuliaSMLM/SMLMData.jl) | Foundational data types (emitters, cameras, SMLD containers) shared across the ecosystem. Most packages re-export what you need. |
| [MicroscopePSFs.jl](https://github.com/JuliaSMLM/MicroscopePSFs.jl) | 2D/3D point-spread-function models and pixel-integration tools for optical simulation and fitting. |

### Simulation

| Package | Description |
| --- | --- |
| [SMLMSim.jl](https://github.com/JuliaSMLM/SMLMSim.jl) | Simulate realistic SMLM data: static super-resolution patterns with blinking photophysics, and diffusion/interaction dynamics for single-particle tracking. |

### Localization

| Package | Description |
| --- | --- |
| [SMLMBoxer.jl](https://github.com/JuliaSMLM/SMLMBoxer.jl) | Particle detection and ROI extraction via difference-of-Gaussians filtering, with GPU acceleration and sCMOS variance weighting. |
| [GaussMLE.jl](https://github.com/JuliaSMLM/GaussMLE.jl) | Fast maximum-likelihood fitting of Gaussian-PSF parameters, with automatic GPU acceleration. |

### Post-processing

| Package | Description |
| --- | --- |
| [SMLMFrameConnection.jl](https://github.com/JuliaSMLM/SMLMFrameConnection.jl) | Link localizations from the same blinking event across frames into single, higher-precision localizations. |
| [SMLMDriftCorrection.jl](https://github.com/JuliaSMLM/SMLMDriftCorrection.jl) | Fiducial-free intra- and inter-dataset drift correction (2D/3D) via entropy minimization. |

### Rendering & visualization

| Package | Description |
| --- | --- |
| [SMLMRender.jl](https://github.com/JuliaSMLM/SMLMRender.jl) | Render point-cloud localizations into images (histogram, Gaussian-blob, or outline) with flexible color mapping. |
| [SMLMView.jl](https://github.com/JuliaSMLM/SMLMView.jl) | WGLMakie-based interactive viewer for N-dimensional microscopy data. |

### Analysis & metrics

| Package | Description |
| --- | --- |
| [SMLMMetrics.jl](https://github.com/JuliaSMLM/SMLMMetrics.jl) | Standardized particle-tracking performance metrics (all 14 Chenouard measures) with optimal track pairing. |

## Getting started

Install the packages you need — for example, a simulate-then-render pipeline:

```julia
using Pkg
Pkg.add(["SMLMData", "SMLMSim", "SMLMRender"])
```

Most packages ship full documentation. Follow the **docs badge** in a repository,
or browse the docs directly at `https://JuliaSMLM.github.io/<Package>.jl/stable`
(for example, [SMLMData docs](https://JuliaSMLM.github.io/SMLMData.jl/stable)).

An ecosystem-wide overview — including shared conventions such as pixel indexing —
lives at [JuliaSMLM.github.io/SMLMDocs.jl/dev](https://JuliaSMLM.github.io/SMLMDocs.jl/dev/).

## Also from this org

- [SMLMClustering.jl](https://github.com/JuliaSMLM/SMLMClustering.jl) — clustering and spatial-statistics backends (DBSCAN, HDBSCAN, Voronoi/SR-Tesseler, and more) for localization data.
- [ModelContextProtocol.jl](https://github.com/JuliaSMLM/ModelContextProtocol.jl) — a Julia implementation of the Model Context Protocol (MCP) for integrating tools and resources with LLMs.

## Contributing

Issues and pull requests are welcome on any repository. Each package is developed
and versioned independently and registered through the Julia General registry.
