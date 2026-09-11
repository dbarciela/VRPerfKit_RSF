# Contributions & Lineage

This repository ([dbarciela/VRPerfKit_RSF](https://github.com/dbarciela/VRPerfKit_RSF)) is directly based on **VRPerfKit RSF v3.2** by [RavenSystem](https://github.com/RavenSystem/VRPerfKit_RSF) (which in turn is a fork of the original [VRPerfKit by fholger](https://github.com/fholger/vrperfkit)).

Version **v4.0** consolidates and modernizes the project, integrating critical bug fixes and performance optimizations developed by various community members across different forks.

---

## Community Contributions & Lineage

| Feature / Fix | Original Author / Fork | Reference / Commits | Affected Files |
| :--- | :--- | :--- | :--- |
| **Base RSF (v1.0 – v3.2)**<br>HRM (Hidden Radial Mask), RDM (Radial Density Mask), and dynamic FPS modes | **RavenSystem**<br>([RavenSystem/VRPerfKit_RSF](https://github.com/RavenSystem/VRPerfKit_RSF)) | Commits `2a92acb` to `b215020` | Base repository |
| **Meta Quest Link Compatibility**<br>Support for `LibOVRRTImpl64_1.dll` and `LibOVRRTImpl32_1.dll` | **biorabbit** / **mledour**<br>([biorabbit/VRPerfKit_RSF](https://github.com/biorabbit/VRPerfKit_RSF)) | PR #8 / Commit `fcba5d9` | `src/oculus/oculus_hooks.cpp` |
| **FFR Vertical Offset**<br>`verticalOffset` configuration to center foveation sweet spot on headset display | **biorabbit**<br>([biorabbit/VRPerfKit_RSF](https://github.com/biorabbit/VRPerfKit_RSF)) | Issue #7 / Commits `5afc952`, `c24c28c` | `src/config.h`, `src/config.cpp`, `src/d3d11/d3d11_variable_rate_shading.cpp`, `vrperfkit_RSF.yml` |
| **OpenVR Per-Frame Memory Optimization**<br>Eliminated per-frame dynamic heap allocations (`new VRTexture...`) | **levi882**<br>([levi882/vrperfkit](https://github.com/levi882/vrperfkit)) | Commit `b6facd9` | `src/openvr/openvr_manager.h`, `src/openvr/openvr_manager.cpp` |
| **2D Texture Array Support**<br>Handling for `ArraySize > 1` in OpenVR resolve subresource | **levi882**<br>([levi882/vrperfkit](https://github.com/levi882/vrperfkit)) | Commit `b6facd9` | `src/openvr/openvr_manager.cpp` |
| **Oculus Swapchain Crash Fix**<br>Prevents double-free crash when both eyes share the same swapchain | **levi882**<br>([levi882/vrperfkit](https://github.com/levi882/vrperfkit)) | Commit `b6facd9` | `src/oculus/oculus_manager.cpp` |
| **Darkened / HDR Typeless Texture Fix**<br>Mapped `DXGI_FORMAT_R16G16B16A16_TYPELESS` to `FLOAT` (GTFO VR / HDR) | **DSprtn** & **Roughy**<br>([DSprtn/vrperfkit](https://github.com/DSprtn/vrperfkit)) | PR #141 / Commit `dbce85d` | `src/openvr/openvr_manager.cpp` |
| **RDM Shaders CMake Build Fix**<br>Added missing HLSL compilation rules for RDM shaders | **biorabbit** & **mledour** | PR #8 / Commit `adcac9c` | `CMakeLists.txt` |
| **Modernization v4.0 & CI Automation**<br>- Modern CMake 4.x compatibility (`CMAKE_POLICY_VERSION_MINIMUM=3.5`)<br>- Seamless fallback between `vrperfkit_RSF.yml` and `vrperfkit.yml`<br>- Self-contained ThirdParty dependencies (LibOVR and NVAPI)<br>- Automated GitHub Actions CI workflow for x64/x86 builds and Releases | **dbarciela**<br>([dbarciela/VRPerfKit_RSF](https://github.com/dbarciela/VRPerfKit_RSF)) | Version 4.0 | `CMakeLists.txt`, `src/dllmain.cpp`, `ThirdParty/`, `.github/workflows/` |
