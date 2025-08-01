---
layout: post
title: Use Terminal
date: 2025-01-05 06:00 -0800
description: Examples of Terminal/Bash commands
author: khoa_pham
categories: [Programming Hub, Tips & Tricks]
tags: [coding]
pin: false
math: true
mermaid: true
toc: true
comments: true
---

After learning some basic terminal commands, you can/should learn Git!  
> Go to [Use Git](https://khoapham1002.github.io/mindpalace/posts/use-git/).

### Navigate Directories   
```bash
# Display the current working directory
pwd

# Change directory
cd path/to/directory

# Move up to the parent directory
cd ..

# Return to the home directory
cd ~

# Navigate to the previous directory
cd -
```

```bash
# List all files in the current directory
ls

# List all files with detailed info (permissions, size, etc.)
ls -la

# List files with human-readable sizes
ls -lh

# List all files in a directory
ls -R [path]
```


### Create and Remove Files/Directories   
```bash
# Create an empty file
touch filename

# Open a file for editing (default editor)
open filename

# Delete a file
rm filename

# Delete multiple files
rm file1 file2 file3

# Force delete without confirmation
rm -f filename
```

```bash
# Create a new directory
mkdir new_directory

# Create multiple nested directories
mkdir -p dir1/dir2/dir3

# Delete a directory (non-empty)
rm -R directory_name

# Force delete a directory and its contents
rm -rf directory_name
```


### Aliases and Shortcuts   
```bash
# Open shell configuration file .zshrc or .bashrc
nano ~/.zshrc
code ~/.zshrc

# View existing aliases
alias

# Add a permanent alias
alias listall="ls -la"
alias jserve="bundle exec jekyll serve"

# Jekyll post shortcut
function jpost() {
  bundle exec jekyll post "$*"
}

# Jupyter notebook to HTML
function nb2html() {
  jupyter nbconvert --to html "$1"
}

# Save (Ctrl + O), then Enter, and Exit (Ctrl + X)
# Reload the shell configuration
source ~/.zshrc
```


### Shortcuts and Commands   
```bash
# Clear the terminal screen
clear     # --- Cmd + K --- also works

# Show all previously executed commands
history

# Run a command from history by its number
!1016     # ![number]
```


### Systems Related (Optional)   
```bash
# Display system info (kernel, architecture, etc.)
uname -a

# View macOS version
sw_vers

# Check your IP address (useful for networking)
ifconfig

# Ping a website or server (test connectivity)
ping example.com
```

```bash
# View file permissions
ls -l

# List all processes
ps -A

# Show system uptime
uptime

# Show memory usage (macOS)
vm_stat

# Show running processes with CPU and memory usage
top
```