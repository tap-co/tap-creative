---
name: tap-creative
description: Generate ad creatives including display banners, audio spots, and video ads. Assets are automatically sized to platform specifications.
---

# Tap Creative Skill

Generate advertising creatives for display, audio, and video formats using AI-powered creative generation.

## Triggers

Activate this skill when the user:
- Asks to create ad creatives, banners, or assets
- Needs audio ads, radio spots, or voiceovers
- Wants to generate video ads or motion graphics
- Mentions ad copy, headlines, or creative concepts
- Needs assets sized for specific platforms

## Setup

### Install the Tap CLI

```bash
npm install -g @tap-co/cli
```

### Authenticate

```bash
tap auth login
```

Enter your API key when prompted. Get an API key at https://docs.tap.co/request-access

### Verify Installation

```bash
tap auth status
tap creative --help
```

## Available Commands

### Generate Creatives

```bash
# Generate display banners
tap creative generate --type display --prompt "Summer sale - 50% off all items" --sizes "300x250,728x90,160x600"

# Generate audio ad
tap creative generate --type audio --prompt "Professional B2B software ad" --duration 30s

# Generate video ad
tap creative generate --type video --prompt "Product launch teaser" --duration 15s

# Save to specific directory
tap creative generate --type display --prompt "Holiday promotion" --output ./assets/
```

### Get Platform Specs

```bash
# View creative specifications for a platform
tap creative specs plt_radio_1234
```

### Output Options

```bash
# Get JSON output for processing
tap creative generate --type audio --prompt "Sale announcement" --json

# Specify output directory
tap creative generate --type display --prompt "Banner ad" --output ./creatives/
```

## Workflow

### 1. Gather Creative Brief
Ask the user for:
- Brand/product name and description
- Campaign goal and key message
- Target audience
- Desired format (display, audio, video)
- Tone/style (professional, playful, urgent, etc.)
- Any brand guidelines or constraints
- Call-to-action

### 2. Determine Specifications
Based on the platform or user needs:

**Display Ads:**
```bash
tap creative generate --type display --prompt "Your message" --sizes "300x250,728x90,160x600"
```
- Standard IAB sizes (300x250, 728x90, 160x600, etc.)
- Social formats (1080x1080, 1200x628, 1080x1920)
- File format (PNG, JPG, GIF, HTML5)

**Audio Ads:**
```bash
tap creative generate --type audio --prompt "Your script" --duration 30s
```
- Duration (15s, 30s, 60s)
- Voice style and gender
- Background music preference
- Podcast vs. radio format

**Video Ads:**
```bash
tap creative generate --type video --prompt "Your concept" --duration 15s
```
- Duration (6s, 15s, 30s)
- Aspect ratio (16:9, 9:16, 1:1)
- Platform (YouTube, TikTok, CTV)

### 3. Generate Creatives
Use Tap's creative generation to produce:
- Multiple variations for A/B testing
- Platform-specific sizing
- Consistent brand application

### 4. Deliver Assets
Provide the user with:
- Generated creative files
- Preview links
- Specifications summary
- Recommendations for optimization

## Example Prompts

- "Create a 30-second radio ad for a summer sale"
- "Generate display banners in all standard IAB sizes"
- "Make a 15-second video ad for Instagram Reels"
- "Write ad copy variations for a new product launch"
- "Create podcast ad scripts for a B2B software product"

## Creative Best Practices

### Display Ads
- Keep text minimal (20% rule)
- Use high-contrast colors
- Clear, prominent CTA button
- Brand logo visible but not dominant

### Audio Ads
- Hook in first 3 seconds
- One clear message per spot
- Conversational tone for podcasts
- Include verbal CTA with easy URL

### Video Ads
- Capture attention in first 2 seconds
- Design for sound-off viewing (captions)
- End with clear CTA and branding
- Optimize for mobile-first viewing

## Scripting & Automation

Combine commands for automation:

```bash
# Generate multiple formats
for type in display audio video; do
  tap creative generate --type $type --prompt "Summer sale promotion" --json > "${type}-creative.json"
done

# Generate all IAB sizes
tap creative generate --type display \
  --prompt "Holiday campaign" \
  --sizes "300x250,728x90,160x600,300x600,320x50" \
  --output ./iab-banners/
```

## Standard Sizes Reference

### IAB Display
| Size | Name |
|------|------|
| 300x250 | Medium Rectangle |
| 728x90 | Leaderboard |
| 160x600 | Wide Skyscraper |
| 300x600 | Half Page |
| 320x50 | Mobile Leaderboard |

### Social Media
| Size | Platform |
|------|----------|
| 1080x1080 | Instagram/Facebook Feed |
| 1200x628 | Facebook/LinkedIn Link |
| 1080x1920 | Stories/Reels |

### Video
| Duration | Use Case |
|----------|----------|
| 6s | YouTube Bumper |
| 15s | TikTok, Instagram |
| 30s | YouTube Pre-roll, CTV |

## Environment Variables

- `TAP_API_KEY` - API key (alternative to `tap auth login`)
- `TAP_API_URL` - API base URL (default: `https://api.tap.co/v1`)

## Resources

- [Tap CLI Documentation](https://docs.tap.co/cli)
- [Tap API Reference](https://docs.tap.co/api)
- [Creative Specs Guide](https://docs.tap.co/api#tag/creatives)
- [Request API Access](https://docs.tap.co/request-access)
