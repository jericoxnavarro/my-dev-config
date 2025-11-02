# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a personal development environment configuration repository for **Windows and macOS** containing:
- **VS Code settings** organized by platform
- **ZSH shell configuration** with Powerlevel10k theme
- **Terminal settings** (Windows Terminal, potentially iTerm2/Terminal.app for Mac)
- **Font files** (Dank Mono, FiraCode, Meslo Nerd Fonts)

The repository is organized with platform-specific subdirectories to manage configurations for different operating systems. Currently contains Windows/WSL (Ubuntu) configurations, with Mac configurations to be added following the same structure.

## Repository Structure

The repository uses a platform-organized structure with subdirectories for each OS:

```
.vscode/
  └── windows/            # VS Code configuration for Windows
      ├── settings.json   # Editor, terminal, and theme settings
      ├── extentions.json # Required VS Code extensions list
      └── windows.code-profile
  # Future: macos/ directory for Mac-specific VS Code settings

.zsh/
  └── windows/            # ZSH configuration for Windows/WSL
      ├── .zshrc          # ZSH configuration with oh-my-zsh & Powerlevel10k
      ├── .p10k.zsh       # Powerlevel10k theme configuration
      └── terminal.settings.json  # Windows Terminal settings
  # Future: macos/ directory for Mac-specific ZSH settings

fonts/                    # Shared font files for all platforms
  ├── Dank Mono/          # MonoLisa alternative font
  ├── DankMono Nerd Font/ # Patched with Nerd Font icons
  ├── FiraCode/           # FiraCode Nerd Font (terminal default)
  └── Meslo/              # MesloLGS Nerd Font variants

images/                   # Screenshots and preview images
```

## Configuration Details

### VS Code Setup (.vscode/windows/settings.json)

**Font Configuration:**
- Editor font: MonoLisa (primary), with fallbacks
- Terminal font: FiraCode Nerd Font
- Font ligatures enabled
- Semantic highlighting with bold styling for functions, classes, types, etc.

**Terminal Configuration:**
- Default shell: ZSH (Linux/WSL)
- Font: FiraCode Nerd Font, size 15
- GPU acceleration enabled
- Custom Vira theme colors applied

**Code Formatting:**
- Format on save enabled
- Prettier as default formatter
- ESLint auto-fix on save
- Single quotes for JavaScript, double quotes for JSX
- Print width: 150
- Trailing commas: all

**Theme:**
- Workbench theme: Vira Teal High Contrast
- Custom color scheme for terminal (Material-inspired)
- Activity bar positioned at top
- Sidebar on right side

**Required Extensions:**
See `.vscode/windows/extentions.json` for the full list. Key extensions include:
- Claude Code, GitHub Copilot, ChatGPT
- Prettier, ESLint
- GitLens
- Python language support
- Better Comments, Bookmarks
- Auto Rename Tag

### ZSH Configuration (.zsh/windows/.zshrc)

**Framework & Theme:**
- oh-my-zsh framework
- Powerlevel10k theme with instant prompt

**Plugins:**
- git: Git aliases and helpers
- z: Directory jumping
- zsh-autosuggestions: Command suggestions
- zsh-syntax-highlighting: Syntax highlighting (must be last)

**Environment:**
- NVM configured for Node.js version management
- Python/pip aliased to python3/pip3
- COLORTERM set to truecolor for better color support

### Windows Terminal (.zsh/windows/terminal.settings.json)

**Profile:**
- Default: Ubuntu-24.04 (WSL)
- Font: FiraCode Nerd Font, size 15
- Color scheme: ViraTheme (custom Material-inspired)

**Key Bindings:**
- Copy: Ctrl+C
- Paste: Ctrl+V
- Find: Ctrl+Shift+F
- Duplicate pane: Alt+Shift+D

## Working with This Repository

### Adding macOS (or other platform) Configurations

When adding macOS configurations (or other platforms):
1. Create platform-specific directories: `.vscode/macos/`, `.zsh/macos/`
2. Follow the same structure as the `windows/` directories:
   - `.vscode/macos/settings.json` - VS Code settings
   - `.vscode/macos/extentions.json` - Extension list
   - `.zsh/macos/.zshrc` - ZSH configuration
   - `.zsh/macos/.p10k.zsh` - Powerlevel10k config
   - Terminal settings for iTerm2 or Terminal.app
3. Update README.md with new platform preview screenshots
4. Fonts directory remains shared across all platforms

### Font Management

All fonts are stored in the `fonts/` directory with subdirectories for each font family. When adding new fonts:
- Keep original files in their own subdirectories
- Include LICENSE files when applicable
- Prefer Nerd Font patched versions for terminal use

### Configuration Sync

This repository serves as a backup and sync point for development environment configurations. To apply configurations:

**VS Code Settings:**
- Copy `.vscode/windows/settings.json` to your VS Code user settings
- Install extensions from `.vscode/windows/extentions.json`

**ZSH Configuration:**
- Copy `.zsh/windows/.zshrc` to `~/.zshrc`
- Copy `.zsh/windows/.p10k.zsh` to `~/.p10k.zsh`
- Ensure oh-my-zsh and Powerlevel10k are installed

**Windows Terminal:**
- Merge settings from `.zsh/windows/terminal.settings.json` into Windows Terminal settings

### Theme Customization

The Vira Teal theme uses the accent color `#80CBC4` (teal) throughout. To change the accent color:
1. Update all instances of `#80CBC4` in `settings.json` (and derived alpha values like `#80CBC433`, `#80CBC480`)
2. Update the same color in `terminal.settings.json` for the cyan values
3. Keep the Material theme terminal colors consistent
