[![DelivOps banner](https://raw.githubusercontent.com/delivops/.github/main/images/banner.png?raw=true)](https://delivops.com)


# ecs-exec Installation (No Dependencies)

These Python scripts require **NO Python packages** - they only use Python standard library and AWS CLI.

## Requirements
- Python 3 (comes with macOS/Linux)
- AWS CLI installed and configured

## Installation

### Option 1: Direct Download
```bash
# Download the script
curl -O https://raw.githubusercontent.com/delivops/ecs-exec/main/ecs-exec
# Or save any of the versions above as 'ecs-exec'

# Make executable
chmod +x ecs-exec

# Move to PATH
sudo mv ecs-exec /usr/local/bin/
```

### Option 2: One-liner
```bash
# Download and install in one command
sudo curl -o /usr/local/bin/ecs-exec https://raw.githubusercontent.com/delivops/ecs-exec/main/ecs-exec && sudo chmod +x /usr/local/bin/ecs-exec
```

### Option 3: Without sudo (user install)
```bash
# Install to user's local bin
mkdir -p ~/.local/bin
curl -o ~/.local/bin/ecs-exec https://raw.githubusercontent.com/delivops/ecs-exec/main/ecs-exec
chmod +x ~/.local/bin/ecs-exec

# Add to PATH if not already there
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.bashrc  # or ~/.zshrc
source ~/.bashrc
```

## Usage
```bash
# Basic usage
ecs-exec production myapp

# With specific task
ecs-exec production myapp arn:aws:ecs:region:account:task/cluster/id

# Use different container name
CONTAINER=nginx ecs-exec production myapp
```

## Uninstall
```bash
sudo rm /usr/local/bin/ecs-exec
# or
rm ~/.local/bin/ecs-exec
```