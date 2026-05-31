# CUDA MATLAB Performance Notes

This repository contains examples and notes for using CUDA together with MATLAB.

## Hardware example

- CPU: Intel Dual Core T4200 2GHz
- GPU: NVIDIA GeForce G103M

## Observations

- GPU programming efficiency is likely affected by the GPU driver and access layer.
- Using MATLAB with CUDA, computation times were reduced by about half on Windows 7.
- On Linux 2.6, the same approach showed a speedup of approximately 4x.
- GPU memory usage during calculations is significantly lower than CPU-only processing.

## Notes

- These results depend on the specific hardware and software environment.
- Modern CUDA and MATLAB versions may produce different performance characteristics.
