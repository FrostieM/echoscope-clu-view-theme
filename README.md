# ECHOSCOPE — a CLU VIEW theme

A sensor-panel theme for [CLU VIEW](https://mr-clu.com/cluview): a thermal chamber for CPU and GPU temperatures that
"breathes" with load, an orbiting planet, CPU / GPU / RAM / storage / network readings, FPS, a clock and a 60-second
temperature graph.

![ECHOSCOPE](preview.png)

- Tested on **CLU VIEW 2.0.6**, Windows.
- Made for a **16:10** panel (for example 1280×800 or 1024×640).
- Built only from standard CLU VIEW widgets: no modified program files, and it works with both panel renderers
  (native and webview).

## Installation

1. Download [`ECHOSCOPE.json`](ECHOSCOPE.json) (open the file and click **Download raw file**).
2. In CLU VIEW open **Profile Manager** → **IMPORT…** and select `ECHOSCOPE.json`.
3. Make the **ECHOSCOPE** profile active on your panel screen.

## Setup after import

Most readings work right away — they come from CLU VIEW's standard sensors: load, temperatures, CPU and GPU power,
CPU fan / pump, VRAM, RAM, storage temperature, network, FPS and the clock.

Three widgets need your own sensors. In the CLU VIEW editor select the widget, open its properties and set **Monitor**:

| Widget | What to pick | Until then |
|---|---|---|
| **CLOCK** (CPU) | your CPU clock sensor, e.g. `Cores (Average)` | `N/A` |
| **VOLTAGE** (CPU) | uses the standard `cpu_voltage` by default; you can pick your CPU's `Core VID` | shows `cpu_voltage` |
| **FANS** (GPU) | your graphics card fan, e.g. `GPU Fan 1` | `N/A` |

The label in the bottom-right corner and the VRAM size are set in the **Text** field of the large main widget,
in the format `label|VRAM in GB`, for example:

```
RTX 4070  /  RYZEN 7|12
```

The default is `CPU  /  GPU|16`.

## Features

- CPU and GPU temperature arcs on a 0–100 °C scale.
- A "breathing" chamber: the pulse speeds up with CPU load; brightness and colour follow load and temperature
  (under heavy load the glow shifts from teal to orange).
- A planet with two satellites whose orbit speeds up with GPU load.
- A graph of CPU and GPU temperatures over the last 60 seconds, with the current values labelled.
- A **TRAFFIC DROP** warning when network speed suddenly falls after a steady transfer of at least 1 MB/s.
- Fonts: Bahnschrift and Consolas, both standard on Windows.

## Known limitations

- The graph assumes that CLU VIEW's sensor history covers about 60 seconds. That holds with the default settings;
  with a different polling interval the time scale will be off.
- In native mode text is slightly softer than in webview mode.
