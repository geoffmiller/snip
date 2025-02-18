# Snip - Command Line Snippet Manager

A vim-style terminal utility for managing and quickly accessing text snippets. Organize your frequently used code snippets, templates, and text blocks into categories and access them from anywhere in your terminal.

![Snip Demo](snip-demo.gif)

> **Note**: Currently tested and supported only on MacOS.

## Features

- Vim-style navigation (h,j,k,l)
- Category-based organization
- Automatic file preview
- Quick clipboard copying
- Clean, flicker-free interface
- Directory and file icons
- Hierarchical navigation

## Installation

Choose one of these three methods to install:

### 1. System-wide Installation (Recommended)

Copy the script to your system's bin directory:
```bash
sudo cp snip /usr/local/bin/ && sudo chmod +x /usr/local/bin/snip
```

### 2. User Bin Directory

Create a personal bin directory and add it to your PATH:
```bash
# Create bin directory if it doesn't exist
mkdir -p ~/bin

# Copy the script
cp snip ~/bin/
chmod +x ~/bin/snip

# Add to PATH (add this line to ~/.zshrc or ~/.bashrc)
export PATH="$HOME/bin:$PATH"

# Reload shell configuration
source ~/.zshrc  # or source ~/.bashrc
```

### 3. Symbolic Link

Create a symbolic link to the script (useful for development):
```bash
sudo ln -s "$(pwd)/snip" /usr/local/bin/snip
```

## Usage

### Basic Commands

- Start the snippet manager:
  ```bash
  snip
  ```

- Show help:
  ```bash
  snip -h
  ```

### Navigation

- `j/k` - Move down/up
- `h` - Go back to parent directory
- `l` - Enter directory or select file
- `Enter` - Enter directory or select file
- `b/Esc` - Go back to parent directory
- `q` - Quit program

### Features

- **Automatic Preview**: File contents are automatically displayed when navigating to a file
- **Directory Icons**: Folders are marked with 📁 and files with 📄
- **Clean Interface**: Flicker-free display with proper line clearing
- **Clipboard Integration**: Selected snippets are automatically copied to clipboard
- **Hierarchical Navigation**: Easily navigate through nested categories

### Directory Structure

Snippets are stored in `~/.snip/` with the following structure:
```
~/.snip/
├── code/
│   ├── python/
│   │   └── hello.py
│   └── javascript/
│       └── fetch.js
├── notes/
│   ├── meeting.txt
│   └── todo.txt
├── other_category/
│   └── ...
└── welcome.txt
```

### Example Usage

1. Create some categories:
```bash
mkdir -p ~/.snip/code/{python,javascript} ~/.snip/notes
```

2. Add some snippets:
```bash
# Add a Python snippet
echo 'def hello_world():
    print("Hello, World!")
    return True' > ~/.snip/code/python/hello.py

# Add a meeting template
echo 'Meeting Notes
Date: 
Attendees: 
Topics:
1. 
2. 
Action Items:
- ' > ~/.snip/notes/meeting_template.txt
```

3. Run `snip` and:
   - Navigate through categories using `j/k`
   - Press `l` or `Enter` to enter directories
   - Navigate to a file to see its preview
   - Press `l` or `Enter` on a file to copy to clipboard
   - Press `h` or `Esc` to go back up a level

## Tips

- Organize snippets into logical categories and subcategories
- Use clear, descriptive filenames
- Add file extensions to help identify snippet types
- Keep snippets focused and reusable
- Use nested directories for better organization

## Troubleshooting

If the `snip` command isn't found after installation:
1. Check if the installation directory is in your PATH:
   ```bash
   echo $PATH
   ```
2. Verify the script is executable:
   ```bash
   ls -l /usr/local/bin/snip
   ```
3. Try reloading your shell:
   ```bash
   source ~/.zshrc  # or source ~/.bashrc
   ```

## Contributing

Feel free to submit issues and enhancement requests! 