# Ardupilot XMLs
This repo contains XMLs and a meson project that uses `mavgen` to generate headers/sources from those XMLs.

## How to Use
Configure meson to create the headers you need:
`meson build -Dlanguage=[insert language here]`

Supported languages can be found in
*   [meson_options.txt](meson_options.txt)
*   `meson configure` - should appear under `project options`.

If you want to change the language, you can run:
`meson --reconfigure build -Dlanguage=[insert language here]`

To actually generate the headers/sources call:
`ninja -C build`

Your generated headers/sources should be found under `build/mavlink/` or `build/mavlink.(py|js|etc)`.

You can also use this project as a meson subproject, it exports the header dir as `mavlink_dep`.
