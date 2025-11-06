# Modifications to Zero-DCE

This is a fork of the original [Zero-DCE repository](https://github.com/Li-Chongyi/Zero-DCE) by Li-Chongyi et al.

## Changes Made

### CPU Support (No GPU Required)
Modified `lowlight_test.py` to support running on CPU-only machines:

1. **Device fallback**: Changed hardcoded `.cuda()` calls to `.to(device)` with automatic CPU/GPU detection
2. **Model loading**: Added `map_location=device` to `torch.load()` to properly load weights on CPU
3. **Windows compatibility**: Fixed directory creation logic to work properly on Windows paths

### Modified Files
- `Zero-DCE_code/lowlight_test.py`

## Original License
This code maintains the original **Attribution-NonCommercial 4.0 International License**.

**For non-commercial and academic research use only.**

## Original Citation
```bibtex
@inproceedings{Zero-DCE,
 author = {Guo, Chunle Guo and Li, Chongyi and Guo, Jichang and Loy, Chen Change and Hou, Junhui and Kwong, Sam and Cong, Runmin},
 title = {Zero-reference deep curve estimation for low-light image enhancement},
 booktitle = {Proceedings of the IEEE conference on computer vision and pattern recognition (CVPR)},
 pages    = {1780-1789},
 month = {June},
 year = {2020}
}
```

## Usage
Same as original, but now works on CPU:
```bash
cd Zero-DCE_code
python lowlight_test.py
```

Note: Processing will be slower on CPU compared to GPU.
