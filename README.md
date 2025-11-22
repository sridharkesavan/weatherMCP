# Weather MCP

A small MCP tool server that uses the U.S. National Weather Service API.  
Provides two tools: `get_alerts(state)` and `get_forecast(latitude, longitude)`.

## Install uv (Homebrew, macOS)

```bash
# Update Homebrew and install uv
brew update
brew install uv

# If Homebrew cannot find `uv`, follow the official installer from:
# https://docs.astral.sh/uv/getting-started/installation/
```

## Clone, install dependencies, and run using uv

```bash
# Clone the repo
git clone https://github.com/sridharkesavan/weatherMCP.git
cd REPO

# Use uv to run pip to install runtime dependencies into uv's managed environment
# (this keeps the environment contained to uv)
uv run -- pip install httpx mcp

# Optionally add these dependencies to uv's project manifest (if you want them tracked)
# (replace with exact uv add syntax if using manifest features)
uv add pypi/httpx pypi/mcp || true

# Run the app under uv so it uses the uv-managed environment
uv run -- python main.py

# For quick testing of a function directly:
uv run -- python -c "import asyncio; from main import get_forecast; print(asyncio.run(get_forecast(37.7749, -122.4194)))"
```

Notes:
- `uv run -- <command>` runs the command inside uv's managed runtime.
- If `uv add` syntax differs for your uv version, follow the uv docs to add packages to the project manifest.
- Replace `git@github.com:USERNAME/REPO.git` with your repository URL.
