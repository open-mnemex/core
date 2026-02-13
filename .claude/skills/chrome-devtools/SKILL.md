---
name: chrome-devtools
description: |
  Control Chrome browser via MCP. MUST load this skill before using any mcp__chrome-devtools__* tools.
  Contains critical best practices: when to use snapshot vs screenshot, avoiding common pitfalls.

  Triggers (EN): "open website", "check my orders", "browse to", "go to URL", "click button",
  "fill form", "take screenshot", "download as PDF", "save page", "inspect network".

  Triggers (中文): "打开网站", "上XX网站", "查看网页", "浏览器", "截图", "下载页面".
---

# Chrome DevTools MCP

Control Chrome browser via MCP tools prefixed with `mcp__chrome-devtools__`.

## 1. Chrome Setup (Required)

Chrome 136+ blocks remote debugging on default profiles for security.
This system uses a custom profile at `~/.chrome-profile` for both daily use and debugging.

### Daily Browsing

Launch via `/Applications/My Chrome.app` (or add to Dock).
This uses the custom profile, so all your logins and extensions are preserved.

### MCP Debugging

```bash
chrome-debug                    # Start Chrome with debugging on port 9222
chrome-debug https://amazon.com # Open specific URL with debugging enabled
```

The command launches Chrome with `--remote-debugging-port=9222` using the custom profile.

### Verify Connection

```bash
curl -s http://127.0.0.1:9222/json/version
```

If successful, returns JSON with Chrome version info.

## 2. Core Tools

| Tool | Purpose |
|------|---------|
| `navigate_page` | Go to URL, back, forward, reload |
| `new_page` | Open URL in new tab (`background: true` for parallel loading) |
| `list_pages` / `select_page` | Manage tabs |
| `click` / `fill` / `hover` | Interact with elements by `uid` |
| `take_snapshot` | Get accessibility tree with element UIDs |
| `take_screenshot` | Capture page or element |
| `list_console_messages` | Debug console output |
| `list_network_requests` | Inspect API calls |
| `performance_start_trace` / `performance_stop_trace` | Profile page performance |

## 3. Standard Workflow

1. `take_snapshot` to get element UIDs
2. Interact using UIDs from snapshot
3. `take_snapshot` again to verify result

### Snapshot vs Screenshot

| Use Case | Tool | Reason |
|----------|------|--------|
| Need to click/fill elements | `take_snapshot` | Provides UIDs for interaction |
| View page content (orders, search results) | `take_screenshot` | Visual overview, avoids large output |
| Extract structured data | `evaluate_script` | Direct data extraction, most efficient |

**Warning:** Complex pages (Amazon, Gmail) may produce snapshots >50K chars.
For read-only tasks, prefer `take_screenshot` or `evaluate_script`.

## 4. Common Tasks

### Save Page as PDF

MCP cannot control native macOS dialogs. Use AppleScript bridge.

**Workflow:**
1. Navigate to target page with MCP
2. Run the save PDF script:

```bash
osascript ~/Documents/.claude/skills/chrome-devtools/scripts/save_pdf.applescript
```

The script: Opens print dialog (Cmd+P) -> Triggers save sheet (Enter) -> Clicks Save.

**Timing:** 3-5 second delays between steps for reliability.

**Rename after download:**
```bash
mv ~/Downloads/"Page Title.pdf" ~/Documents/00_Vault/03_Financial/Receipts/YYYY-MM-DD_Receipt_Vendor_desc.pdf
```

### Download Images

Two methods for downloading images from web pages.

**Method A: JS + curl (Recommended)**

Extract image URLs with JavaScript, then download with curl.

```javascript
// Extract image URLs via evaluate_script
() => {
  return Array.from(document.querySelectorAll('img[src]'))
    .map(img => img.src)
    .filter(src => src.startsWith('http'))
    .slice(0, 10);  // Limit results
}
```

```bash
# Download with curl
curl -sL "https://example.com/image.jpg" -o ~/Downloads/image.jpg
```

**Method B: AppleScript Right-Click**

For images that can't be extracted via JS (CSS background images, etc.):

```bash
osascript ~/Documents/.claude/skills/chrome-devtools/scripts/save_image.applescript
```

### Batch Operations

For multiple pages, open all first, then iterate:

```
# 1. Open all URLs in background tabs
new_page(url1, background=true)
new_page(url2, background=true)

# 2. Iterate through tabs
list_pages() -> for each pageId:
  select_page(pageId, bringToFront=true)
  # Run save_pdf.applescript
  # Rename downloaded file
```

**Batch image download:**
```bash
for url in "${image_urls[@]}"; do
  filename=$(basename "$url")
  curl -sL "$url" -o "~/Downloads/$filename" &
done
wait
```

## 5. Troubleshooting

| Issue | Solution |
|-------|----------|
| Connection refused | Run `chrome-debug` first to start Chrome with debugging |
| Page closed | Use `list_pages` to see available pages |
| Element not found | Take fresh snapshot; UIDs change after page updates |
| Click doesn't work | Verify element is visible and not covered |
| PDF save fails | Increase delays; ensure Chrome is frontmost |
| Native dialog timeout | Use AppleScript, not MCP |
| Chrome crashes on start | Remove lock files: `rm -f ~/.chrome-profile/Singleton*` |

## 6. Reference

### Profile Location

- **Profile path:** `~/.chrome-profile`
- **Debugging port:** 9222 (localhost only)

### Security Considerations

Remote debugging port (9222) allows any local app to control Chrome.
The port only binds to localhost (127.0.0.1), not external interfaces.
Avoid sensitive operations (banking, passwords) while debugging is active.
