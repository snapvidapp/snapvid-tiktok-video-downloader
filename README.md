# SnapVid — TikTok Video Downloader & Converter Library

[![npm version](https://img.shields.io/badge/npm-v1.2.0-blue.svg)](https://en.snapvid.app/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Node.js](https://img.shields.io/badge/Node.js-%3E%3D16.0.0-green.svg)](https://nodejs.org/)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://en.snapvid.app/)

A lightweight, powerful, and developer-friendly Node.js library that allows developers to [download TikTok videos without watermark](https://en.snapvid.app/) in high-definition (HD & Full HD).

Backed by the core parsing algorithms behind **[SnapVid](https://en.snapvid.app/)**, this library provides full access to TikTok media streams, photo carousels, and audio tracks with zero external binary dependencies.

---

## 🌐 Live Web Version

> **Not a developer?** If you are looking for an instant, browser-based utility that works without installing packages or writing code, use the official web tool:  
> 👉 **[SnapVid — TikTok Video Downloader](https://en.snapvid.app/)**

---

## ✨ Features

- 🎯 **Watermark-Free Video Downloads:** Automatically resolve clean MP4 streams without the bouncing TikTok logo or creator ID overlay.
- 🖼️ **[TikTok Slideshow Downloader](https://en.snapvid.app/download-tiktok-slide):** Extract full-resolution individual photos from carousel posts or render them into video presentations.
- ⏳ **[TikTok Story Downloader](https://en.snapvid.app/download-tiktok-stories):** Fetch temporary 24-hour public stories before they expire.
- 🎵 **[Extract TikTok MP3 Audio](https://en.snapvid.app/download-tiktok-mp3):** Isolate soundtrack and audio streams directly into standard MP3 audio files.
- ⚡ **High Performance:** Fast parsing pipeline optimized for low-latency production applications.
- 📱 **Cross-Platform:** Works across Linux, macOS, and Windows server environments.

---

## 📦 Installation

Install via `npm`:

```bash
npm install snapvid-tiktok-downloader
```

Or via `yarn`:

```bash
yarn add snapvid-tiktok-downloader
```

---

## 🚀 Usage

### 1. Basic Video Download (Without Watermark)

```javascript
const TikTokDownloader = require('snapvid-tiktok-downloader');

// Initialize client
const downloader = new TikTokDownloader({
  output: './downloads',
  format: 'mp4',
  quality: 'high'
});

// Download clean video
downloader.download('https://www.tiktok.com/@username/video/1234567890123456789')
  .then(file => {
    console.log(`Video successfully saved to: ${file.path}`);
  })
  .catch(err => {
    console.error('Download error:', err.message);
  });
```

---

### 2. Downloading TikTok Photo Slideshows

For carousel posts containing multiple images, use the built-in [TikTok slideshow handler](https://en.snapvid.app/download-tiktok-slide):

```javascript
// Download all photos from a TikTok photo post
downloader.downloadSlideshow('https://www.tiktok.com/@username/video/1234567890123456789')
  .then(response => {
    console.log(`Downloaded ${response.images.length} full-resolution photos.`);
    response.images.forEach(img => console.log(`- ${img.path}`));
  })
  .catch(err => {
    console.error('Slideshow extraction failed:', err.message);
  });
```

---

### 3. Extracting Audio / MP3

If you only require the sound effect or background music, extract the audio directly via the [MP3 extractor](https://en.snapvid.app/download-tiktok-mp3):

```javascript
downloader.downloadAudio('https://www.tiktok.com/@username/video/1234567890123456789')
  .then(audio => {
    console.log(`Audio track saved to: ${audio.path}`);
  });
```

---

## 📖 API Documentation

### Constructor Options

| Option | Type | Default | Description |
| :--- | :--- | :--- | :--- |
| `output` | `string` | `'./downloads'` | Target directory for storing downloaded files |
| `format` | `string` | `'mp4'` | Media container output (`mp4`, `mp3`, `webm`) |
| `quality` | `string` | `'high'` | Desired resolution profile (`low`, `medium`, `high`) |
| `filenamePattern` | `string` | `'{username}-{id}'` | Dynamic naming pattern for downloaded assets |

### Main Methods

- `download(url, options)`: Resolves and downloads a clean video without watermark.
- `downloadSlideshow(url, options)`: Downloads all underlying images from a photo-mode TikTok.
- `downloadAudio(url, options)`: Extracts and saves the standalone audio track.
- `getInfo(url)`: Fetches metadata, author details, view counts, and available download streams.

---

## 🖥️ WebUI Integration

A lightweight web demonstration server is included for testing:

```bash
# Start local demonstration server
npm run webui
```

Then visit `http://localhost:3000` in your browser. For production deployments, refer to the [SnapVid Web Architecture](https://en.snapvid.app/).

---

## 🤝 Contributing

Contributions are welcome! If you find bugs or want to request a feature:

1. Fork the repository
2. Create your branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## ⚖️ License & Disclaimer

Distributed under the **MIT License**. See `LICENSE` for details.

**Disclaimer:** This library is an independent open-source tool and is not affiliated, associated, authorized, endorsed by, or in any way officially connected with TikTok, ByteDance, or any of their subsidiaries. Respect copyright and only download content with appropriate permission from the creator.

---

## 🙏 Acknowledgements

- **[SnapVid App](https://en.snapvid.app/)** — For core media processing algorithms and web interface inspiration.
- Open-source Node.js and HTTP parser communities.
