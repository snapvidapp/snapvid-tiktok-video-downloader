About The Project
A powerful yet simple library that allows you to [download TikTok videos without watermarks](https://snapvid.app). Inspired by GetFVID.io, this open-source solution provides developers with the tools to integrate TikTok video downloading functionality into their applications.
Our library supports both regular TikTok videos and TikTok slideshows, ensuring comprehensive content access in high quality formats.
Features

🎯 Watermark-Free Downloads: Remove those distracting TikTok watermarks completely

🎥 High Definition Quality: Maintain the original video quality (up to 1080p)

🖼️ TikTok Slideshow Downloader: Extract slideshows and photo collections from TikTok

🔄 Multiple Format Support: Download in MP4, MP3, and more

⚡ Fast Processing: Optimized algorithms for quick downloads

🔑 API Access: Simple RESTful API for integration

📱 Cross-Platform Support: Works on all major platforms


Installation

bashnpm install tiktok-downloader
# or
yarn add tiktok-downloader
Usage
Basic Usage
javascriptconst TikTokDownloader = require('tiktok-downloader');

// Initialize downloader
const downloader = new TikTokDownloader({
  output: './downloads',
  format: 'mp4',
  quality: 'high'
});

// Download a TikTok video without watermark
downloader.download('https://www.tiktok.com/@username/video/1234567890123456789')
  .then(file => {
    console.log(`Video downloaded to: ${file.path}`);
  })
  .catch(err => {
    console.error('Download failed:', err.message);
  });
[Download TikTok Slideshow]([https://example.com](https://snapvid.app/download-tiktok-slide))
javascript// For downloading slideshows with all images
downloader.downloadSlideshow('https://www.tiktok.com/@username/video/1234567890123456789')
  .then(files => {
    console.log(`Slideshow downloaded with ${files.length} images`);
    files.forEach(file => console.log(`- ${file.path}`));
  })
  .catch(err => {
    console.error('Slideshow download failed:', err.message);
  });
API Documentation

Class: TikTokDownloader

Constructor Options

OptionTypeDefaultDescriptionoutputstring'./downloads'Output directory for downloaded filesformatstring'mp4'Output format (mp4, mp3, webm)qualitystring'high'Video quality (low, medium, high)filenamePatternstring'{username}-{id}'Pattern for naming downloaded files

Methods

download(url, options): Download a single TikTok video

downloadSlideshow(url, options): Download all images from a TikTok slideshow

downloadBatch(urls, options): Download multiple TikTok videos

getInfo(url): Get metadata about a TikTok video

WebUI Integration

This library also includes a simple web interface for demonstration:

bash# Start the web server

npm run webui

Then open http://localhost:3000 in your browser to use the web interface.

License

Distributed under the MIT License. See LICENSE for more information.

Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are greatly appreciated.

Fork the Project

Create your Feature Branch (git checkout -b feature/AmazingFeature)

Commit your Changes (git commit -m 'Add some AmazingFeature')

Push to the Branch (git push origin feature/AmazingFeature)

Open a Pull Request

Acknowledgements

Snapvid.app for inspiration

TikTok API Documentation

All our contributors and supporters
