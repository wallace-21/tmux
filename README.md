# Tmux Configuration

This repository contains a customized tmux configuration file that enhances productivity with improved key bindings, visual enhancements, and useful plugins.

## Features

### Core Settings
- **256-color terminal support** for better color rendering
- **Custom prefix key** (`Ctrl+a`) instead of the default `Ctrl+b`
- **Mouse support** enabled for easier pane selection and resizing
- **Vi-style key bindings** for copy mode

### Custom Key Bindings

| Key Combination | Action |
|----------------|--------|
| `Ctrl+a` | Prefix key (instead of default `Ctrl+b`) |
| `Prefix + -` | Split window horizontally |
| `Prefix + =` | Split window vertically |
| `Prefix + r` | Reload tmux configuration |
| `Prefix + m` | Toggle pane zoom (maximize/minimize) |

### Pane Resizing (Repeatable)
| Key | Action |
|-----|--------|
| `Prefix + h` | Resize pane left by 5 units |
| `Prefix + j` | Resize pane down by 5 units |
| `Prefix + k` | Resize pane up by 5 units |
| `Prefix + l` | Resize pane right by 5 units |

*Note: These keys are repeatable - you can hold the prefix key and press the resize key multiple times.*

### Copy Mode Bindings
| Key | Action |
|-----|--------|
| `v` | Begin visual selection (in copy mode) |
| `y` | Copy selection (in copy mode) |

## Plugins

This configuration uses [TPM (Tmux Plugin Manager)](https://github.com/tmux-plugins/tpm) to manage plugins:

### Included Plugins
- **vim-tmux-navigator**: Seamless navigation between vim and tmux panes
- **tmux-themepack**: Beautiful themes for tmux (using powerline/default/cyan theme)
- **tmux-resurrect**: Save and restore tmux sessions
- **tmux-continuum**: Automatic saving and restoring of tmux sessions

### Plugin Features
- **Session persistence**: Your tmux sessions will automatically save and restore
- **Pane content capture**: The actual content of panes is saved during session saves
- **Automatic restore**: Sessions are automatically restored when tmux starts

## Installation

### Prerequisites
1. Install tmux
2. Install TPM (Tmux Plugin Manager):
   ```bash
   git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
   ```

### Setup
1. Copy the configuration to your home directory:
   ```bash
   cp .tmux.conf ~/.tmux.conf
   ```

2. Reload tmux configuration:
   ```bash
   tmux source-file ~/.tmux.conf
   ```

3. Install plugins by pressing `Prefix + I` (capital i) inside a tmux session

## Usage Tips

### Getting Started
- Start a new tmux session: `tmux new-session -s mysession`
- Attach to existing session: `tmux attach-session -t mysession`
- List sessions: `tmux list-sessions`

### Working with Panes
- Split horizontally: `Prefix + -`
- Split vertically: `Prefix + =`
- Navigate between panes: Use mouse or vim-tmux-navigator
- Resize panes: `Prefix + h/j/k/l`
- Zoom pane: `Prefix + m`

### Copy Mode
- Enter copy mode: `Prefix + [`
- Start selection: `v`
- Copy selection: `y`
- Paste: `Prefix + ]`

## Customization

You can modify the configuration by editing `~/.tmux.conf`. After making changes, reload the configuration with `Prefix + r`.

### Common Customizations
- Change theme: Modify the `@themepack` setting
- Add more plugins: Add `set -g @plugin 'plugin-name'` lines
- Adjust key bindings: Use `bind` and `unbind` commands
- Modify colors: Adjust terminal and color settings

## Troubleshooting

### Plugins Not Working
- Ensure TPM is installed correctly
- Press `Prefix + I` to install plugins
- Check plugin documentation for specific requirements

### Key Bindings Not Working
- Verify tmux configuration is loaded: `Prefix + r`
- Check for conflicting key bindings
- Ensure you're using the correct prefix key (`Ctrl+a`)

### Colors Not Displaying Correctly
- Verify your terminal supports 256 colors
- Check `$TERM` environment variable
- Try different terminal emulators if issues persist
