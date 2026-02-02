# tap-creative

Agent skill for generating ad creatives including display banners, audio spots, and video ads.

## Installation

```bash
npx skills add tap-co/tap-creative
```

## What it does

This skill teaches AI agents how to:

- **Generate display ads** - Banners in standard IAB sizes and social formats
- **Create audio ads** - Radio spots and podcast ads with voiceover
- **Produce video ads** - Short-form video for YouTube, TikTok, CTV

All assets are automatically sized to platform specifications.

## Supported Agents

Works with any agent that supports the [Agent Skills](https://agentskills.io) standard:

- Claude Code
- Cursor
- GitHub Copilot
- Cline
- OpenAI Codex
- Windsurf
- And 15+ more

## Example Prompts

Once installed, try asking your agent:

- "Create a 30-second radio ad for a summer sale"
- "Generate display banners in all standard IAB sizes"
- "Make a 15-second video ad for Instagram Reels"
- "Write ad copy variations for a new product launch"
- "Create podcast ad scripts for a B2B software product"

## Creative Formats

### Display
- 300x250, 728x90, 160x600 (IAB standard)
- 1080x1080, 1200x628, 1080x1920 (social)
- PNG, JPG, GIF, HTML5

### Audio
- 15s, 30s, 60s durations
- MP3/WAV format
- Podcast and radio styles

### Video
- 6s, 15s, 30s durations
- 16:9, 9:16, 1:1 aspect ratios
- YouTube, TikTok, CTV platforms

## MCP Integration

For real-time creative generation, configure the [Tap MCP server](https://docs.tap.co/mcp):

```json
{
  "mcpServers": {
    "tap": {
      "url": "https://mcp.tap.co",
      "transport": "sse"
    }
  }
}
```

## Links

- [Tap API Documentation](https://docs.tap.co/api)
- [Creative Specs Guide](https://docs.tap.co/api#tag/creatives)
- [Agent Skills Spec](https://agentskills.io)

## License

MIT
