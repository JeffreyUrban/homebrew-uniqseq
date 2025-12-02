# Homebrew Tap for uniqseq

This is the official Homebrew tap for [uniqseq](https://github.com/JeffreyUrban/uniqseq), a stream-based deduplication tool for repeating sequences.

## Installation

### Quick Install

```bash
brew tap JeffreyUrban/uniqseq
brew install uniqseq
```

### One-Line Install

```bash
brew install JeffreyUrban/uniqseq/uniqseq
```

## What Gets Installed

When you install `uniqseq` via Homebrew, you get:

- ✅ **uniqseq** - The main CLI tool for stream-based deduplication
- ✅ **Python dependencies** - All Python packages in an isolated virtualenv

## Features

- **Isolated environment** - Python packages don't conflict with your system Python
- **Easy updates** - `brew upgrade uniqseq` to get the latest version
- **Automatic formula updates** - New releases are published automatically

## Usage

After installation, the `uniqseq` command is available in your PATH:

```bash
# Check version
uniqseq --version

# Process a file
uniqseq --window-size 3 input.log

# Process from stdin
cat input.log | uniqseq --window-size 3

# Get help
uniqseq --help
```

## Updating

```bash
# Update Homebrew
brew update

# Upgrade uniqseq
brew upgrade uniqseq
```

## Uninstalling

```bash
# Remove uniqseq
brew uninstall uniqseq

# Remove the tap
brew untap JeffreyUrban/uniqseq
```

## Documentation

- **Main Project**: https://github.com/JeffreyUrban/uniqseq
- **PyPI**: https://pypi.org/project/uniqseq/

## Requirements

- **macOS** 11.0+ (Big Sur) or **Linux**
- **Python** 3.14+ (provided by Homebrew)

## Troubleshooting

### Command not found after installation

```bash
# Ensure Homebrew's bin is in your PATH
echo 'export PATH="/opt/homebrew/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

### Check installation

```bash
# Verify uniqseq is installed
brew list uniqseq

# Test basic functionality
echo -e "line1\nline2\nline3\nline1\nline2\nline3" | uniqseq --window-size 3
```

### Reinstall

```bash
brew reinstall uniqseq
```

## Development

This tap uses automated workflows to update the formula when new versions are released:

1. A new release is created in the main repository
2. The release workflow triggers this repository via `repository_dispatch`
3. The update workflow waits for the PyPI release
4. A pull request is automatically created with the updated formula
5. After review, the PR is merged to publish the update

For more details, see [`.github/workflows/update-formula.yml`](.github/workflows/update-formula.yml).

## Contributing

Issues and pull requests should be submitted to the main repository:
https://github.com/JeffreyUrban/uniqseq/issues

Formula-specific issues can be reported here:
https://github.com/JeffreyUrban/homebrew-uniqseq/issues

## License

The formula in this repository is licensed under the MIT License.

The uniqseq software itself is also MIT licensed. See the [main repository](https://github.com/JeffreyUrban/uniqseq) for details.
