# ZelAI SDK Documentation

Welcome to the official documentation for **zelai-cloud-sdk** - the TypeScript/JavaScript SDK for ZelStudio.com Cloud AI Generation API.

## Quick Navigation

| Guide | Description |
|-------|-------------|
| [Getting Started](Getting-Started) | Installation, API key setup, initialization |
| [Image Generation](Image-Generation) | Text-to-image, image editing, AI upscaling |
| [Video Generation](Video-Generation) | Image-to-video creation |
| [LLM & Streaming](LLM-Text-Generation) | Text generation, streaming, OpenAI-compatible API |
| [OpenAI Compatibility](OpenAI-Compatibility) | Framework integrations: LangChain, Vercel AI, LlamaIndex |
| [AI Agent Integration](AI-Agent-Integration) | Enable AI agents (Claude, GPT, etc.) to use the SDK |
| [CDN Operations](CDN-Operations) | Downloads, watermarks, format conversion |
| [WebSocket API](WebSocket-API) | Real-time generation with progress updates |
| [API Reference](API-Reference) | Complete endpoint documentation |
| [Examples](Examples) | Full code examples |
| [Troubleshooting](Troubleshooting) | Common issues, debug mode, best practices |

## Features

- **Text-to-Image** - Generate images from text prompts with 14 style presets
- **Image-to-Image** - Edit and transform existing images
- **AI Image Upscale** - Upscale images 2-4x using AI
- **Image-to-Video** - Create videos from static images
- **LLM Text Generation** - Generate text with memory, JSON support, and streaming
- **OpenAI-Compatible API** - Drop-in `/v1/chat/completions` endpoint
- **Image Description (Vision)** - Analyze images with LLM
- **Built-in Watermarking** - Apply custom watermarks to content
- **WebSocket Support** - Real-time generation with progress updates
- **Full TypeScript Support** - Comprehensive type definitions

## Quick Install

```bash
npm install zelai-cloud-sdk
```

## Quick Example

```typescript
import { createClient, STYLES, FORMATS } from 'zelai-cloud-sdk';

const client = createClient('zelai_pk_your_api_key');

// Generate an image
const image = await client.generateImage({
  prompt: 'A beautiful sunset over mountains',
  style: STYLES.realistic,
  format: FORMATS.landscape
});

console.log('Image ID:', image.imageId);
```

## Need Help?

- [Troubleshooting Guide](Troubleshooting)
- [GitHub Issues](https://github.com/ZelStudio/zelai-cloud-sdk/issues)
- [Changelog](https://github.com/ZelStudio/zelai-cloud-sdk/blob/main/CHANGELOG.md)

---

**Version:** 1.10.0 | [View on npm](https://www.npmjs.com/package/zelai-cloud-sdk)
