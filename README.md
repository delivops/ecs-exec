[![DelivOps banner](https://raw.githubusercontent.com/delivops/.github/main/images/banner.png?raw=true)](https://delivops.com)

#  Easy ECS Container Shell Access

`ecs-exec` is a simple tool to quickly access the shell of a container running in AWS ECS. It uses the AWS CLI and the AWS Session Manager Plugin to make this process effortless.


**Zero-dependency Python script** that makes ECS container access effortless:

✅ **No Python packages to install** - uses only standard library  
✅ **Single file download** - no complex setup or build process  
✅ **Works everywhere** - macOS, Linux, Windows, any Python 3 environment  
✅ **One-liner installation** - get started in seconds

## Requirements

- Python 3 (comes with macOS/Linux)
- AWS CLI installed and configured
- AWS Session Manager Plugin installed

## Usage

```bash
# Basic usage
ecs-exec production myapp

# With specific task
ecs-exec production myapp arn:aws:ecs:region:account:task/cluster/id

# Use different container name (default: app)
CONTAINER=nginx ecs-exec production myapp
```

## Installation

**Quick 2-step setup** - install the AWS plugin, then download our script:

### Install AWS Session Manager Plugin

```bash
# macOS
brew install --cask session-manager-plugin

# Linux
curl "https://s3.amazonaws.com/session-manager-downloads/plugin/latest/ubuntu_64bit/session-manager-plugin.deb" -o "session-manager-plugin.deb" && sudo dpkg -i session-manager-plugin.deb
```

### Install ecs-exec Script

#### Option 1: Direct Download

```bash
# Download the script
curl -O https://raw.githubusercontent.com/delivops/ecs-exec/main/ecs-exec
# Or save any of the versions above as 'ecs-exec'

# Make executable
chmod +x ecs-exec

# Move to PATH
sudo mv ecs-exec /usr/local/bin/
```

#### Option 2: One-liner

```bash
# Download and install in one command
sudo curl -o /usr/local/bin/ecs-exec https://raw.githubusercontent.com/delivops/ecs-exec/main/ecs-exec && sudo chmod +x /usr/local/bin/ecs-exec
```

#### Option 3: Without sudo (user install)

```bash
# Install to user's local bin
mkdir -p ~/.local/bin
curl -o ~/.local/bin/ecs-exec https://raw.githubusercontent.com/delivops/ecs-exec/main/ecs-exec
chmod +x ~/.local/bin/ecs-exec

# Add to PATH if not already there
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.bashrc  # or ~/.zshrc
source ~/.bashrc
```

## Uninstall

```bash
sudo rm /usr/local/bin/ecs-exec
# or
rm ~/.local/bin/ecs-exec
```
