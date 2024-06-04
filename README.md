# polybar-metar

A METAR data display for polybar.

## Requirements

1. polybar, or some other program that can swallow shell scripts
2. Bash, of a modern variety
3. python-metar
4. Font Awesome 6 Free

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

    metar.sh [OPTIONS] [--] <AIRPORT CODE>

      -h, -?, -v, --help                 This message
      -c,         --use-metric, --si     Use metric units
      -m,         --no-humidity          Don't print humidity information
      -w,         --no-wind              Don't print wind speed/direction
      -p,         --no-pressure          Don't print atmospheric pressure
      -s,         --no-sky-conditions    Don't print sky conditions
      -n,         --no-glyphs            Don't print FontAwesome glyphs
      -d <char>,  --delimiter <char>     Use <char> as a delimiter instead of
                                         "|", only works with glyphs turned off.

An airport code for your local airport can be found at
https://www.iata.org/en/publications/directories/code-search/

If the glyphs are not showing up, make sure that you have Font Awesome 6 Free
installed. Some fonts may also override the Font Awesome glyphs.

## License

Beatbot is released under the [BSD license](https://opensource.org/licenses/BSD-3-Clause).
