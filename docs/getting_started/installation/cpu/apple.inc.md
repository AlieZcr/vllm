# --8<-- [start:installation]

vLLM has experimental support for macOS with Apple silicon. For now, users shall build from the source vLLM to natively run on macOS.

Currently the CPU implementation for macOS supports FP32 and FP16 datatypes.

!!! warning
    There are no pre-built wheels or images for this device, so you must build vLLM from source.

# --8<-- [end:installation]
# --8<-- [start:requirements]

- OS: `macOS Sonoma` or later
- SDK: `XCode 15.4` or later with Command Line Tools
- Compiler: `Apple Clang >= 15.0.0`

# --8<-- [end:requirements]
# --8<-- [start:set-up-using-python]

# --8<-- [end:set-up-using-python]
# --8<-- [start:pre-built-wheels]

# --8<-- [end:pre-built-wheels]
# --8<-- [start:build-wheel-from-source]

After installation of XCode and the Command Line Tools, which include Apple Clang, execute the following commands to build and install vLLM from the source.

```bash
git clone https://github.com/vllm-project/vllm.git
cd vllm
pip install -r requirements/cpu.txt
pip install -e .
```

!!! note
    On macOS the `VLLM_TARGET_DEVICE` is automatically set to `cpu`, which currently is the only supported device.

#### Troubleshooting

If the build has error like the following snippet where standard C++ headers cannot be found, try to remove and reinstall your
[Command Line Tools for Xcode](https://developer.apple.com/download/all/).

```text
[...] fatal error: 'map' file not found
          1 | #include <map>
            |          ^~~~~
      1 error generated.
      [2/8] Building CXX object CMakeFiles/_C.dir/csrc/cpu/pos_encoding.cpp.o

[...] fatal error: 'cstddef' file not found
         10 | #include <cstddef>
            |          ^~~~~~~~~
      1 error generated.
```

# --8<-- [end:build-wheel-from-source]
# --8<-- [start:pre-built-images]

# --8<-- [end:pre-built-images]
# --8<-- [start:build-image-from-source]

# --8<-- [end:build-image-from-source]
# --8<-- [start:extra-information]
# --8<-- [end:extra-information]
