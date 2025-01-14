# NEWS

This file contains significant user-visible changes for each version.
For full changelog, use `git log`

## 0.4.0 (2021-12-31)

Compile with wlroots 0.15.0

This release contains lots of internal changes, fixes and  new features.
A big thank you goes out to @ARDiDo, @bi4k8, @Joshua-Ashton,
@jlindgren90, @Consolatis, @telent and @apbryan. The most notable
feature-type changes are listed below:

- The config option `<lab><xdg_shell_server_side_deco>` has changed to
  `<core><decoration>` (breaking change)
- Add support for the following wayland protocols:
    - `pointer_constraints` and `relative_pointer` - mostly for gaming.
      Written-by: @Joshua-Ashton
    - `viewporter` - needed for some games to fake modesets.
      Written-by: @Joshua-Ashton
    - `wlr_input_inhibit`. This enables swaylock to be run.
      Written-by: @telent
    - `wlr_foreign_toplevel`. This enables controlling windows from clients
      such as waybar.
    - `idle` and `idle_inhibit` (Written-by: @ARDiDo)
- Support fullscreen mode.
- Support drag-and-drop. Written-by: @ARDiDo
- Add the following config options:
    - Load default keybinds on `<keyboard><default />`
    - `<keyboard><repeatRate>` and `<keyboard><repeatDelay>`
    - Specify distance between views and output edges with `<core><gap>`
    - `<core><adaptiveSync>`
    - Set menu item font with `<theme><font place="MenuItem">`
    - Allow `<theme><font>` without place="" attribute, thus enabling
      simpler config files
    - Support `<mousebind>` with `contexts` (e.g. `TitleBar`, `Left`,
      `TLCorner`, `Frame`), `buttons` (e.g. `left`, `right`), and
      `mouse actions` (e.g. `Press`, `DoubleClick`). Modifier keys are
      also supported to handle configurations such as `alt` + mouse button
      to move/resize windows. (Written-by: @bi4k8, @apbryan)
    - `<libinput>` configuration. Written-by: @ARDiDo
    - `<resistance><screenEdgeStrength>`
- Support for primary selection. Written-by: @telent
- Support 'alt-tab' on screen display when cycling between windows
  including going backwards by pressing `shift` (Written-by: @Joshua-Ashton)
  and cancelling with `escape` (Written-by: @jlindgren90)
- Add the following theme options:
    - set buttons colors individually (for iconify, close and maximize)
    - `window.(in)active.label.text.color`
    - `window.label.text.justify`
    - OSD colors
- Show application title in window decoration title bar
- Handle double click on window decoration title bar
- Support a 'resize-edges' area that is wider than than the visible
  window decoration. This makes it easier to grab edges to resize
  windows.
- Add window actions 'MoveToEdge', 'ToggleMaximize', 'Close', 'Iconify',
  'ToggleDecorations', 'ToggleFullscreen', 'SnapToEdge', 'Focus', 'Raise',
  'Move', 'MoveToEdge', 'Resize', 'PreviousWindow', 'ShowMenu'
- Add labwc.desktop for display managers
- layer-shell:
    - Take into account exclusive areas of clients (such as panels) when
      maximizing windows
    - Support popups
- Handle xwayland `set_decorations` and xdg-shell-decoration requests.
  Written-by: @Joshua-Ashton
- Handle view min/max size better, including xwayland hint support.
  Written-by: @Joshua-Ashton
- Handle xwayland move/resize events. Written-by: @Joshua-Ashton
- Support audio and monitor-brightness keys by default
- Catch ctrl-alt-F1 to F12 to switch tty
- Support `XCURSOR_THEME` and `XCURSOR_SIZE` environment variables
- Support submenus including inline definitions

## 0.3.0 (2021-06-28)

Compile with wlroots 0.14.0

- Add config options `<focus><followMouse>` and `<focus><raiseOnFocus>`
  (provided-by: Mikhail Kshevetskiy)
- Do not use Clearlooks-3.4 theme by default, just use built-in theme
- Fix bug which triggered Qt application segfault

## 0.2.0 (2021-04-15)

Compile with wlroots 0.13.0

- Support wlr-output-management protcol for setting output position, scale
  and orientation with kanshi or similar
- Support server side decoration rounded corners
- Change built-in theme to match default GTK style
- Add labwc-environment(5)
- Call `wlr_output_enable_adaptive_sync()` if `LABWC_ADAPTIVE_SYNC` set

## 0.1.0 (2021-03-05)

Compile with wlroots 0.12.0 and wayland-server >=1.16

- Support xdg-shell and optionally xwayland-shell
- Show xbm buttons for maximize, iconify and close
- Support layer-shell protocol (partial)
- Support damage tracking to reduce CPU usage
- Support very basic root-menu implementation
- Re-load config and theme on SIGHUP
- Support simple configuration to auto-start applications, set
  environment variables and specify theme, font and keybinds.
- Support some basic theme settings for window borders and title bars
- Support basic actions including Execute, Exit, NextWindow, Reconfigure and 
  ShowMenu

