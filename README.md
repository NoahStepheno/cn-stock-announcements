# OpenClaw Stock Announcements Plugin

This plugin for **OpenClaw** allows your AI agents to query official listed company announcements from the Shenzhen Stock Exchange (SZSE) and Shanghai Stock Exchange (SSE).

## Features
- Search by exact stock code (`000001` for SZSE, `600000` for SSE).
- Search by keyword in the announcement title (e.g., `年报`, `分红`).
- Filter announcements by exact date and time range (`2026-03-15 00:00:01`).
- Supports querying multiple stocks simultaneously.

## Installation

Ensure you have the required dependencies:

```bash
pip install requests openclaw
```

## Quick Start (OpenClaw)

Simply import the plugin and `use()` it with your OpenClaw client:

```python
from openclaw2 import OpenClaw
from stock_plugin import StockAnnouncementPlugin

# Initialize OpenClaw client
client = OpenClaw.remote(api_key="your_api_key")

# Install the stock announcements plugin
client.use(StockAnnouncementPlugin())

# Let the agent fetch the data!
results = client.pipeline([
    "请帮我查询 000001 和 600000 从 2024-03-15 00:00:01 到 2024-03-16 00:00:01 的年报公告"
])

print(results[-1])
```
