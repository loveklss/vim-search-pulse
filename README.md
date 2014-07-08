# The vim search pulse: easily locate where the cursor is after a search

## Description

When you perform a search, the cursor jumps to the closest match. It's often
hard to locate it's new position. With this plugin the cursor line (by default)
or the search pattern will "pulse" thus requiring your eyes attention.

For the cursor line to be set only in the active window you may want to install
this plugin: https://github.com/vim-scripts/CursorLineCurrentWindow

Activate the cursor line highlighing by putting `set cursorline` in your .vimrc
file.

### Cursor line pulse animation:
![cursor line pulse](http://i.imgur.com/ukZuti2.gif)

### Pattern pulse animation:
![pattern pulse](http://i.imgur.com/jFyjW3f.gif)

## Installation

Use pathogen or a pathogen compatible plugin manager.

## Configuration

Sets whether the cursor line pulses (default is cursor_line):

    let g:vim_search_pulse_mode = 'cursor_line'

or just the search pattern:

    let g:vim_search_pulse_mode = 'pattern'

If you want to set your own mappings, do:

    let g:vim_search_pulse_disable_auto_mappings = 1

Otherwise the plugin will do the following for you:

    nmap n n<Plug>PulseCursorLine
    nmap N N<Plug>PulseCursorLine
    nmap * *<Plug>PulseCursorLine
    nmap # #<Plug>PulseCursorLine
    " Pulses cursor line on first match
    " when doing search with / or ?
    cmap <enter> <Plug>PulseFirst

The pulse duration is 200 milliseconds by default. You can set your own using
the following global variable. For example:

    let g:vim_search_pulse_duration = 400

The colors used by the pulse are `[237, 238, 239, 240, 241]` (gray scale) by
default. A color map can be found at:
http://www.calmar.ws/vim/256-xterm-24bit-rgb-color-chart.html

You can set your own and as many as you want using the following global
variable. For example (green scale):

    let g:vim_search_pulse_color_list = [22, 28, 34, 40, 46]

If you are using gvim, these are the default colors:

    `['#3a3a3a', '#444444', '#4e4e4e', '#585858', '#606060']`

To disable/enable set the value of `g:vim_search_pulse_disable` to 0 or 1

## Credits

This plugin is inspired by:

* https://github.com/LStinson/Vim/blob/master/plugin/pulse.vim
* https://github.com/ivyl/vim-bling from which I borrowed some ideas
* http://redd.it/1o7t2a

The animated gif was created using http://www.cockos.com/licecap/
