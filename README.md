# Snip - Command Line Snippet Manager

A vim-style terminal utility for managing and quickly accessing text snippets. Organize your frequently used code snippets, templates, and text blocks into categories and access them from anywhere in your terminal.

![Snip Demo](snip-demo.gif)

## Features

- Vim-style navigation (h,j,k,l)
- Category-based organization
- Live preview of snippets
- Quick clipboard copying
- Simple and intuitive interface

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
- `h` - Go back to categories
- `l` - Select item
- `Enter` - Select item
- `b/Esc` - Go back to categories
- `q` - Quit program

### Directory Structure

Snippets are stored in `~/.snip/` with the following structure:
```
~/.snip/
├── code/
│   ├── hello.py
│   └── fetch.js
├── notes/
│   ├── meeting.txt
│   └── todo.txt
└── other_category/
    └── ...
```

### Example Usage

1. Create some categories:
```bash
mkdir -p ~/.snip/code ~/.snip/notes
```

2. Add some snippets:
```bash
# Add a Python snippet
echo 'def hello_world():
    print("Hello, World!")' > ~/.snip/code/hello.py

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
   - Navigate to a category using `j/k`
   - Press `l` or `Enter` to view snippets
   - Navigate to a snippet
   - Press `l` or `Enter` to copy to clipboard

## Tips

- Organize snippets into logical categories
- Use clear, descriptive filenames
- Add file extensions to help identify snippet types
- Keep snippets focused and reusable

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