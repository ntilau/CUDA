# CUDA MATLAB Examples

This repository contains MATLAB and CUDA sample code for GPU-accelerated FFT and simulation.

## Central Repository Structure

- `Matlab_CUDA_1.1/` - MATLAB scripts, CUDA source files, and example workflows for FFT acceleration.
- `configMinGW64/` - MinGW configuration helpers for building MATLAB MEX files on Windows.
- `configMinGW64/mexopts-win64/` - 64-bit MinGW configuration for Windows MATLAB builds.
- `nvmex_fix/` - Setup notes and environment fixes for building with `nvmex`.
- `TESTS.md` - Optional repository test or verification notes.

## Getting Started

1. Install MATLAB.
2. Install the NVIDIA CUDA Toolkit.
3. Set CUDA environment variables:
   - `CUDA_PATH` should point to the CUDA installation directory.
   - If needed, set `CUDA_LIB_PATH` to the CUDA library folder.
4. Use `mex` or `nvmex` to build the example MEX files.

## Build Example

### Build CUDA FFT MEX files

On Windows:

    mex fft2_cuda.c -IC:\CUDA\include -LC:\CUDA\lib -lcudart -lcufft
    mex fft2_cuda_sp_dp.c -IC:\CUDA\include -LC:\CUDA\lib -lcudart -lcufft
    mex ifft2_cuda.c -IC:\CUDA\include -LC:\CUDA\lib -lcudart -lcufft

### Build the CUDA simulation example with nvmex

    nvmex -f nvmexopts.bat Szeta.cu -IC:\cuda\include -LC:\cuda\lib -lcufft -lcudart

## Notes

- Performance depends on the GPU driver, CUDA toolkit version, and MATLAB version.
- Older results showed about 2x speedup on Windows and 4x speedup on Linux with MATLAB + CUDA.
- GPU memory usage is typically lower than CPU-only execution for these workloads.
- This repository was originally tested with older toolchains; modern setups may require updated build flags and paths.

## Subdirectory Details

- `Matlab_CUDA_1.1/README.txt` contains detailed build and runtime instructions for the MATLAB examples.
- `nvmex_fix/ReadMe.txt` contains environment and path notes for `nvmex`.
- `configMinGW64/` contains Windows-specific build scripts and `mexopts` configuration.

## Keep in Mind

This root README is the central guide. If you need platform-specific setup or build details, follow the subdirectory documentation first.
