# SCC2020Tool

[![Build Status](https://github.com/davidhien/SCC2020Tool.jl/actions/workflows/CI.yml/badge.svg?branch=main)](https://github.com/davidhien/SCC2020Tool.jl/actions/workflows/CI.yml?query=branch%3Amain)

[scc2020](https://bitbucket.org/mkerber/chain_complex_format/src/master/) is a file format for chain complexes of multiparameter persistence modules created by Michael Lesnik and Michael Kerber.

SCC2020Tool.jl is a simple tool to generate a SCC files from boundary matrices and column grades.

## Usage

this package provides a single function:
````
    write_complex_scc2020(filename_or_io, boundary_matrices, grades; kwargs...)

A chain complex

```
C₁ → C₂ → C₃ → …
```

is represented by a list of boundary matrices `M₁, M₂, M₃, …` and grades `g₁, g₂, …`, where `Mᵢ`
is the boundary map `Cᵢ → Cᵢ₋₁` and `gᵢ` is a list of grades for the generators of `Cᵢ`.

# Arguments
- `filename_or_io::String` or `IO`: The output file name or an IO stream.
- `boundary_matrices`: The list of boundary matrices.
- `grades`: The list of grades for the generators of each chain group.
- `op_params`: (optional) A list of parameter indices to reverse. Default is `Int[]`.
- `n_params`: (optional) The number of parameters. Default is inferred from the first element in `grades[1]`.
- `field`: (optional) The field. Default is `"GF(2)"`.
````