# PNPM Zsh Autocompletion Setup

Zsh autocompletion scripts for pnpm that will complete both package.json scripts and standard pnpm commands.

## Files

- `_pnpm` - Full-featured completion script

## Installation

### Option 1: Oh My Zsh Custom Plugin (Recommended)

1. Copy the completion script to your Oh My Zsh custom plugins directory:

```bash
# Create the plugin directory
mkdir -p ~/.oh-my-zsh/custom/plugins/pnpm

# Copy the simple version (recommended)
cp _pnpm ~/.oh-my-zsh/custom/plugins/pnpm/_pnpm
```

2. Add the plugin to your `.zshrc`:

```bash
plugins=(... pnpm)
```

3. Reload your shell:

```bash
source ~/.zshrc
```

### Option 2: Manual Installation

1. Copy the script to your zsh completion directory:

```bash
# Find your zsh completion directory
echo $FPATH

# Copy to the first directory in FPATH (usually ~/.oh-my-zsh/completions)
cp _pnpm ~/.oh-my-zsh/completions/_pnpm
```

2. Reload completions:

```bash
autoload -U compinit && compinit
```

## Features

### Standard Commands
- Completes all standard pnpm commands (add, remove, install, update, etc.)
- Shows descriptions for each command
- Supports command aliases (i, rm, up, etc.)

### Package.json Scripts
- Automatically detects and completes scripts from package.json
- Shows script descriptions
- Works with `pnpm run <script>` or direct `pnpm <script>`

### Context-Aware Completion
<!--- `pnpm add` - Shows package name prompt-->
- `pnpm remove` - Completes with installed packages from package.json
<!--- `pnpm why` - Completes with installed packages-->
<!--- `pnpm store` - Completes with store subcommands-->
<!--- `pnpm cache` - Completes with cache subcommands-->

## Usage Examples

```bash
# Type 'pnpm ' and press TAB to see all commands and scripts
pnpm <TAB>

# Type 'pnpm remove ' and press TAB to see installed packages
pnpm remove <TAB>
```
## Customization

I commented out several completions, please feel free to uncomment them in the `_pnpm` file if you want those features.
