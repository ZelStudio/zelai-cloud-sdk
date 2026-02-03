# Getting Started

This guide will help you install the SDK, obtain an API key, and make your first API call.

## Table of Contents

- [Installation](#installation)
- [Getting an API Key](#getting-an-api-key)
- [Initialization](#initialization)
- [Quick Start](#quick-start)
- [Client Options](#client-options)

---

## Installation

```bash
npm install zelai-cloud-sdk
```

or with yarn:

```bash
yarn add zelai-cloud-sdk
```

**Requirements:**
- Node.js 18 or higher
- TypeScript 5.0+ (for TypeScript projects)

---

## Getting an API Key

To use this SDK, you need an API key.

### Request Access

1. Fill out the [API Access Request Form](https://forms.zelstudio.com/api-access)
2. We'll review your request within 24-48 hours
3. Once approved, you'll receive your API key via email

### Contact

- Twitter/X: [@ZelStudio](https://x.com/ZelStudio)


---

## Initialization

### Basic Setup

```typescript
import { createClient } from 'zelai-cloud-sdk';

const client = createClient('zelai_pk_your_api_key_here');
```

### With Options

```typescript
import { createClient } from 'zelai-cloud-sdk';

const client = createClient('zelai_pk_your_api_key_here', {
  timeout: 300000,      // Request timeout (default: 5 minutes)
  debug: true,          // Enable debug logging
  wsAutoReconnect: true // Auto-reconnect WebSocket (default: true)
});
```

---

## Quick Start

### REST API Example

```typescript
import { createClient, STYLES, FORMATS } from 'zelai-cloud-sdk';

const client = createClient('zelai_pk_your_api_key_here');

// Generate an image
const image = await client.generateImage({
  prompt: 'a majestic lion in the savanna at sunset',
  style: STYLES.cine.id,
  format: FORMATS.landscape.id
});

console.log(`Generated image ID: ${image.imageId}`);
```

### WebSocket Example

```typescript
import { createClient, STYLES, FORMATS } from 'zelai-cloud-sdk';

const client = createClient('zelai_pk_your_api_key_here');

// Connect to WebSocket
await client.wsConnect();

// Generate image via WebSocket
const wsImage = await client.wsGenerateImage({
  prompt: 'a futuristic city at night',
  style: STYLES.cine.id,
  format: FORMATS.landscape.id
});

console.log(`WebSocket Image ID: ${wsImage.result.imageId}`);

// Always close when done
await client.close();
```

---

## Client Options

| Option | Type | Default | Description |
|--------|------|---------|-------------|
| `apiKey` | `string` | required | Your ZelAI API key |
| `baseUrl` | `string` | `https://api.zelstudio.com` | API base URL |
| `timeout` | `number` | `300000` | Request timeout in ms (5 min) |
| `debug` | `boolean` | `false` | Enable debug logging |
| `wsAutoReconnect` | `boolean` | `true` | Auto-reconnect on disconnect |
| `wsReconnectIntervalMs` | `number` | `1000` | Initial reconnect delay |
| `wsMaxReconnectDelayMs` | `number` | `30000` | Max reconnect delay |
| `wsPingIntervalMs` | `number` | `30000` | Ping interval for keepalive |

---

## Next Steps

- [Image Generation](Image-Generation) - Generate and edit images
- [Video Generation](Video-Generation) - Create videos from images
- [LLM & Streaming](LLM-Text-Generation) - Text generation with streaming

---

← [Home](Home) | [Image Generation](Image-Generation) →
