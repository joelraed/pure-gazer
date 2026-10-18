# Pure Gazer — Shimmer Reverb

Independent stereo granular shimmer/delay audio effect in C++17, developed from the [MPC Gazer v0.4 prototype](https://github.com/joelraed/mpc-gazer).

The original v0.4 DSP has **worked on an ARMv7 MPC One running HAKAI 3.9.0**, with approximately 13–18 CPU percentage points per instance in a Mini D project. The **Pure Gazer identity and binaries are not yet hardware-tested**.

Pure Gazer is an independent plugin name. The MPC One support is an unofficial platform port, not a product or endorsement by Akai/inMusic. No proprietary third-party DLL is included.

## DSP and presets

Stereo multi-delay, granular octave shimmer, feedback, predelay, diffusion, highpass/damping and width; includes Celestial Glow, Soft Halo, Crystal Air and Dark Drift preset definitions.

## Build on desktop

```sh
cmake -S . -B build
cmake --build build -j
ctest --test-dir build --output-on-failure
```

## ARM / MPC build

The GitHub Actions workflows on `main` build experimental ARMv7 artifacts using the [sd88me/mpc-vst-plugins](https://github.com/sd88me/mpc-vst-plugins) wrapper framework. The artifacts **are not yet an installer**. Back up your current `MPC.settings` before any device installation.

## Compatibility and identity

Pure Gazer uses a **different VST unique ID** (`PGzr`, `0x50477a72`) and binary (`PureGazer.so`), deliberately avoiding collisions with the previous MPC Gazer version (`MGzr`). Existing MPC projects with MPC Gazer will not automatically migrate to Pure Gazer. Keep the working older version until you finish testing.

## Roadmap

1. Verify Pure Gazer build artifacts and separate device registration.
2. Implement a clean ethereal interface skin in the host-supported UI format.
3. Optimize CPU while preserving the long decaying feedback and Celestial Glow tone.
4. Benchmark release candidates on MPC One.
