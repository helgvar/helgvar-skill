# Magento 2 MCP Servers Setup

These MCP servers require Node.js. Install Node.js first, then configure them.

## Prerequisites
```bash
# Install Homebrew (if not installed)
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Install Node.js
brew install node
```

## 1. elgentos/magento2-dev-mcp (25+ tools)
Live access to cache, DI, plugins, observers, cron, database, deploy.
```bash
claude mcp add magento2-dev -- npx -y @elgentos/magento2-dev-mcp
```

## 2. Midhun-edv/magento-coding-standard-mcp (7 tools)
83+ Magento coding standards, security validation, theme presets (Hyva/Luma/Breeze).
```bash
git clone https://github.com/Midhun-edv/magento-coding-standard-mcp.git ~/magento-coding-standard-mcp
cd ~/magento-coding-standard-mcp && npm install && npm run build
claude mcp add magento-coding-standard -- node ~/magento-coding-standard-mcp/dist/index.js
```

## 3. boldcommerce/magento2-mcp (14 tools)
REST API access: products, orders, stock, revenue, customer data.
Requires Magento API token (System > Integrations in admin).
```bash
git clone https://github.com/boldcommerce/magento2-mcp.git ~/magento2-mcp
cd ~/magento2-mcp && npm install && npm run build
claude mcp add magento2-bold -- node ~/magento2-mcp/dist/index.js
```

## 4. GitHub CLI (for PR reviews, issue management)
```bash
brew install gh
gh auth login
```
