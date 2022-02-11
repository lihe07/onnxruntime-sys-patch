## onnxruntime-sys-patch

Fixed onnxruntime-sys not being able to access GitHub in China. 

Due to the interference of GitHub in China, when building onnxruntime-sys, it will display:

```
thread 'main' panicked at 'ERROR: Failed to download https://github.com/microsoft/onnxruntime/releases/download/v1.8.1/.....'
```

This crate replaces the original link and uses a mirror server to download the library files.

## Usage

Add the following to the project configuration file Cargo.toml that uses onnxruntime or onnxruntime-sys:

```toml
[patch.crates-io]
onnxruntime-sys = { package = "onnxruntime-sys-patch" }
```

