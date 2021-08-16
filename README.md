# Silence Speed MPV Script
Speeds up silent parts of videos played using MPV

Inspired by:
- [CaryKH Jumpcutter](https://www.youtube.com/watch?v=DQ8orIurGxw)
- [Skip Silence Extension](https://github.com/vantezzen/skip-silence)

## Installation
Copy `silence-speed.lua` to `[MPV Config Folder]/scripts`

## Configuration
This plugin supports MPV's `script-opts`.

### Valid Options
|Option|Default|Description|
|---|---|---|
|quietness|-30|The threshold for silence in dB|
|duration|0.167|The minimum duration of silence required to speed up|
|end_offset|0.1|The period from the end of silence to slowing down|
|silence_speed|2.5|The speed to play silent portions of the video at|

## Implementation/Quirks
To avoid dropped frames and major desync, the speed jumps up to `silence_speed`
and then ramps down, ending slightly before the end of the silence (controlled
by `end_offset`).

## License
Licensed under the terms of the MIT License (see LICENSE for details).

Derived from [skip-intro by rui-ddc](https://github.com/rui-ddc/skip-intro),
which is itself based on [work by detuur](https://github.com/detuur/mpv-scripts)
