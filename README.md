# amdgpu-backlight

Recently acquired a new laptop with an **AMD Ryzen 5 PRO 3500U** processor that provides an [**AMD Radeon RX Vega 8**](https://www.notebookcheck.net/AMD-Radeon-RX-Vega-8-GPU-Benchmarks-and-Specs.260180.0.html). Long story short, there's a bug that prevents from setting `xbacklight` values... but it's still possible to `echo` values from 0 to 255 to the `amdgpu_bl0` brightness file, so this script was born.

**Remember, this software is provided AS IS. Run at your own risk**

## help

```
usage: amdgpu-backlight [-h] [-s] [-q] [--confirm] [percent]

A duct-tape solution to a very annoying bug.

positional arguments:
  percent      Set brightness to this percentage.

optional arguments:
  -h, --help   show this help message and exit
  -s, --step   Increase/Decrease brightness by a step instead.
  -q, --query  Get current brightness percentage.
  --confirm    This software is provided AS IS. Please, confirm that you're completely sure that you want to run this script. This argument is required.
```

### i3

There's also a companion script for `i3status`: `i3status-amdgpu-backlight`, which you can use like so:

```
bar {
        status_command i3status | /path/to/bin/i3status-amdgpu-backlight
        ...
}
```

### sudoers.d

You might want to create a file named `/etc/sudoers.d/amdgpu-backlight` with this content:

```
YOU ALL = (ALL:ALL) NOPASSWD: /usr/bin/amdgpu-backlight
```

## Bugs?

If you find one, [report it](/lvm/amdgpu-backlight/issues) please.

## License

see [LICENSE](LICNESE)
