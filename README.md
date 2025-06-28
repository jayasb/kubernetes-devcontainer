# Kubernetes Development Environment with Dev Containers

A production-ready development environment for cloud-native applications using Python, Node.js, and Kubernetes. This repository provides a complete containerized development setup that works identically across different machines and platforms.

## What's Included

- **Python 3.11** - Latest stable Python runtime
- **Node.js 20** - Latest LTS Node.js with npm
- **Docker-in-Docker** - Build and run containers inside your dev environment
- **kubectl** - Kubernetes command-line tool
- **k3d** - Lightweight Kubernetes clusters in Docker
- **VS Code Extensions** - Pre-configured extensions for Python, JavaScript, and Kubernetes development

## Quick Start

### Option 1: GitHub Codespaces (Cloud)

1. **Open in Codespaces**:
   - Click the green "Code" button on this repository
   - Select "Codespaces" tab
   - Click "Create codespace on main"

2. **Wait for setup** (2-3 minutes)
   - k3d will be automatically installed
   - Kubernetes cluster will be ready to use

3. **Verify setup**:
   ```bash
   python --version
   node --version
   k3d version
   kubectl get nodes
   ```

### Option 2: Local Development

#### Prerequisites
- [Docker Desktop](https://www.docker.com/products/docker-desktop/) installed and running
- [VS Code](https://code.visualstudio.com/) with [Dev Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)

#### Setup Steps
1. **Clone this repository**:
   ```bash
   git clone <repository-url>
   cd <repository-name>
   ```

2. **Open in VS Code**:
   ```bash
   code .
   ```

3. **Reopen in container**:
   - VS Code will show a popup asking to "Reopen in Container"
   - Click "Reopen in Container"
   - Or use Command Palette: `Dev Containers: Reopen in Container`

4. **Wait for automatic setup** (2-3 minutes)
   - All tools will be automatically installed and configured

5. **Verify everything is ready**:
   ```bash
   python --version
   node --version
   k3d version
   kubectl get nodes
   ```

## Port Forwarding

The following ports are automatically forwarded:

- **3000** - React/Next.js development servers
- **8080** - General application port

Additional ports can be forwarded through VS Code's Ports panel.

## Customization

### Adding Python Packages

Add packages to your `requirements.txt` or install directly:

```bash
pip install fastapi uvicorn requests
```

### Adding Node.js Packages

```bash
npm install express react next.js
```

### Modifying the Environment

Edit `.devcontainer/devcontainer.json` to:
- Change Python or Node.js versions
- Add additional VS Code extensions
- Include more development tools
- Configure additional port forwarding

Example customization:
```json
{
  "features": {
    "ghcr.io/devcontainers/features/python:1": {
      "version": "3.12"
    },
    "ghcr.io/devcontainers/features/node:1": {
      "version": "18"
    }
  }
}
```

## Resources

- [Development Containers Specification](https://containers.dev/)
- [VS Code Dev Containers Documentation](https://code.visualstudio.com/docs/devcontainers/containers)
- [GitHub Codespaces Documentation](https://docs.github.com/en/codespaces)
- [k3d Documentation](https://k3d.io/)
- [Kubernetes Documentation](https://kubernetes.io/docs/)

---

**Star this repository** if you find it helpful! It helps others discover this setup and motivates continued development.
