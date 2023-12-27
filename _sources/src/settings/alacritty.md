# Alacritty_Config: alacritty.yml

```yml

# Configuration for Alacritty, the GPU enhanced terminal emulator.

window:
  # Startup Mode (changes require restart)
  #
  # Values for `startup_mode`:
  #   - Windowed
  #   - Maximized
  #   - Fullscreen
  #
  # Values for `startup_mode` (macOS only):
  #   - SimpleFullscreen
  startup_mode: SimpleFullscreen

  # Background opacity
  opacity: 0.9

# Font configuration
font:
  # Normal (roman) font face
  normal:
    family: PT Mono

    # The `style` can be specified to pick a specific face.
    style: Regular

  # Bold font face
  bold:
    family: PT Mono

    # The `style` can be specified to pick a specific face.
    style: Bold

  # Italic font face
  italic:
    family: PT Mono

    # The `style` can be specified to pick a specific face.
    style: Italic

  # Bold italic font face
  bold_italic:
    family: PT Mono

    # The `style` can be specified to pick a specific face.
    style: Bold Italic

  # Point size
  size: 16.0

# Colors (One Dark)
colors:
  primary:
    background: '#282c34'
    foreground: '#abb2bf'
  cursor:
    text:       CellBackground
    cursor:     '#528bff' # syntax-cursor-color
  selection:
    text:       CellForeground
    background: '#3e4451' # syntax-selection-color
  normal:
    black:      '#5c6370' # mono-3
    red:        '#e06c75' # red 1
    green:      '#98c379'
    yellow:     '#e5c07b' # orange 2
    blue:       '#61afef'
    magenta:    '#c678dd'
    cyan:       '#56b6c2'
    white:      '#828997' # mono-2

selection:
  save_to_clipboard: true

cursor:
  # Cursor style
  #
  # Values for `style`:
  #   - ▇ Block
  #   - _ Underline
  #   - | Beam
  style: Block

live_config_reload: true

shell:
  program: /bin/zsh
  args:
    - --login

mouse:
  hide_when_typing: true

# Mouse bindings
mouse_bindings:
  - { mouse: Right, action: Paste }

# Key bindings
key_bindings:
  # (macOS only)
  #- { key: Key0,   mods: Command,         action: ResetFontSize    }
  #- { key: Equals, mods: Command,         action: IncreaseFontSize }
  #- { key: Add,    mods: Command,         action: IncreaseFontSize }
  #- { key: Minus,  mods: Command,         action: DecreaseFontSize }
  #- { key: K,      mods: Command,         action: ClearHistory     }
  #- { key: K,      mods: Command,         chars: "\x0c"            }
  - { key: V,      mods: Command,         action: Paste            }
  - { key: C,      mods: Command,         action: Copy             }
  #- { key: H,      mods: Command,         action: Hide             }
  #- { key: M,      mods: Command,         action: Minimize         }
  #- { key: Q,      mods: Command,         action: Quit             }
  #- { key: W,      mods: Command,         action: Quit             }
  #- { key: F,      mods: Command|Control, action: ToggleFullscreen }

  #- { key: Paste,                    action: Paste                            }
  #- { key: Copy,                     action: Copy                             }
  #- { key: L,         mods: Control, action: ClearLogNotice                   }
  #- { key: L,         mods: Control, chars: "\x0c"                            }
  #- { key: PageUp,    mods: Shift,   action: ScrollPageUp,   mode: ~Alt       }
  #- { key: PageDown,  mods: Shift,   action: ScrollPageDown, mode: ~Alt       }
  #- { key: Home,      mods: Shift,   action: ScrollToTop,    mode: ~Alt       }
  #- { key: End,       mods: Shift,   action: ScrollToBottom, mode: ~Alt       }

```
