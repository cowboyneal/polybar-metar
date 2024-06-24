# polybar-metar

A METAR data display for [Polybar](https://github.com/polybar/polybar).

**polybar-metar** retrieves the METAR data from an airport of your choosing
and displays it in a concise manner, using the icons from
[Font Awesome](https://fontawesome.com/).

![Screenshot](https://raw.githubusercontent.com/cowboyneal/polybar-metar/master/polybar-metar-screenshot.png)

## Requirements

1. **Polybar**, or some other program that can swallow shell scripts
2. **Bash**, of a modern variety
3. GNU **getopt**, if using BSD
4. **bc**, if not installed by default
5. **python-pymetar** or **python-metar**
6. **Font Awesome 6 Free**

## Installation

Place the script somewhere where it can be run, and reference it from your
**Polybar**'s config.ini. The following is provided as an example entry for
the module.

```ini
[module/metar]
type = custom/script
exec = ~/.config/polybar/metar.sh -s KOSU
interval = 180
label = %output%
```

## Usage

metar.sh [OPTIONS] [--] &lt;AIRPORT CODE&gt;

<table>
  <tr>
    <td>-h, -?, -v</td>
    <td>--help</td>
    <td>This message</td>
  </tr>
  <tr>
    <td>-c</td>
    <td>--use-metric, --si</td>
    <td>Use metric units</td>
  </tr>
  <tr>
    <td>-m</td>
    <td>--no-humidity</td>
    <td>Don't print humidity information</td>
  </tr>
  <tr>
    <td>-w</td>
    <td>--no-wind</td>
    <td>Don't print wind speed/direction</td>
  </tr>
  <tr>
    <td>-p</td>
    <td>--no-pressure</td>
    <td>Don't print atmospheric pressure</td>
  </tr>
  <tr>
    <td>-s</td>
    <td>-&#65279;-&#65279;no-&#65279;sky-&#65279;conditions</td>
    <td>Don't print sky conditions</td>
  </tr>
  <tr>
    <td>-n</td>
    <td>--no-glyphs</td>
    <td>Don't print FontAwesome glyphs</td>
  </tr>
  <tr>
    <td>-&#65279;d&nbsp;&lt;char&gt;</td>
    <td>-&#65279;-&#65279;delimiter&nbsp;&lt;char&gt;</td>
    <td>Use &lt;char&gt; as a delimiter instead of "&#124;", only works
        with glyphs turned off.</td>
  </tr>
</table>

An airport code for your local airport can be found at
https://www.iata.org/en/publications/directories/code-search/

If the glyphs are not showing up, make sure that you have Font Awesome 6 Free
installed. Some fonts may also override the Font Awesome glyphs.

## Bugs

Surely.

## License

polybar-metar is released under the [BSD license](https://opensource.org/licenses/BSD-3-Clause).
