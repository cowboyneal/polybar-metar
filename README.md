# polybar-metar

A METAR data display for [Polybar](https://github.com/polybar/polybar).

**polybar-metar** goes and gets the METAR data from an airport of your choosing
and displays it in a concise manner, using the icons from [Font Awesome](https://fontawesome.com/).

![Screenshot](https://raw.githubusercontent.com/cowboyneal/polybar-metar/master/polybar-metar-screenshot.png)

## Requirements

1. Polybar, or some other program that can swallow shell scripts
2. Bash, of a modern variety
3. bc, if not installed by default
4. python-metar
5. Font Awesome 6 Free

## Installation

Place the script somewhere where it can be run, and reference it from your
polybar's config.ini. The following is provided as an example entry for the
module.

    [module/metar]
    type = custom/script
    exec = ~/.config/polybar/metar.sh -s KOSU
    interval = 180
    label = %output%

## Usage

metar.sh [OPTIONS] [--] &lt;AIRPORT CODE&gt;

| short option    | long option              | definition
| ---             | ---                      | ---
| -h, -?, -v      | --help                   | This message
| -c              | --use-metric, --si       | Use metric units
| -m              | --no-humidity            | Don't print humidity information
| -w              | --no-wind                | Don't print wind speed/direction
| -p              | --no-pressure            | Don't print atmospheric pressure
| -s              | --no-sky-conditions      | Don't print sky conditions
| -n              | --no-glyphs              | Don't print FontAwesome glyphs
| -d &lt;char&gt; | --delimiter &lt;char&gt; | Use &lt;char&gt; as a delimiter instead of "&#124;", only works with glyphs turned off.

An airport code for your local airport can be found at
https://www.iata.org/en/publications/directories/code-search/

If the glyphs are not showing up, make sure that you have Font Awesome 6 Free
installed. Some fonts may also override the Font Awesome glyphs.

## License

Beatbot is released under the [BSD license](https://opensource.org/licenses/BSD-3-Clause).
