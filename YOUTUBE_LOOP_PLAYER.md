# YouTube Loop Player Tool

## 🎯 Overview

A simple web-based tool that plays YouTube videos on loop with automatic variation in playback speed and start positions, simulating human-like viewing behavior.

## ✨ Features

- **Auto-Loop**: Videos automatically restart when they finish
- **Variable Speed**: Each loop plays at a different speed (0.5x - 2x)
- **Variable Start Position**: Each loop starts at a different position (within first 30% of video)
- **Real-time Stats**: View current playback speed, loop count, and position
- **Clean UI**: Modern, responsive interface with visual status indicators

## 🚀 How to Use

1. Open `youtube-loop-player.html` in any modern web browser
2. Paste a YouTube video URL or Video ID in the input field
3. Click "Start Loop Player" button
4. The video will start playing and automatically loop with variations

### Supported URL Formats

The tool accepts multiple YouTube URL formats:
- Full URL: `https://www.youtube.com/watch?v=dQw4w9WgXcQ`
- Short URL: `https://youtu.be/dQw4w9WgXcQ`
- Embed URL: `https://www.youtube.com/embed/dQw4w9WgXcQ`
- Video ID only: `dQw4w9WgXcQ`

## 🎮 How It Works

### Loop Behavior

Each time the video completes:
1. **Loop counter** increments
2. **New random speed** is selected from: 0.5x, 0.75x, 1.0x, 1.25x, 1.5x, 1.75x, 2.0x
3. **New start position** is randomly chosen (within first 30% of video duration)
4. Video automatically restarts from the new position at the new speed

This creates a natural, human-like viewing pattern where:
- You don't always watch from the beginning
- You sometimes watch faster or slower
- Each viewing session feels unique

## 📊 Information Panel

The tool displays real-time information:
- **Status**: Current playback status (Playing/Paused) with visual indicator
- **Current Speed**: Playback rate for current loop
- **Loop Count**: Total number of times the video has looped
- **Start Position**: Where the current loop started
- **Video Duration**: Total length of the video

## 🛠️ Technical Details

### Technologies Used
- HTML5
- CSS3 (with animations and gradients)
- Vanilla JavaScript
- YouTube IFrame API

### Browser Compatibility
Works on all modern browsers that support:
- ES6 JavaScript
- YouTube IFrame API
- CSS3 features

### Requirements
- Internet connection (to load YouTube API and videos)
- Modern web browser (Chrome, Firefox, Safari, Edge)
- JavaScript enabled

## 🎨 Customization

You can easily customize the tool by modifying:

### Speed Range
Edit the `getRandomSpeed()` function to change available speeds:
```javascript
function getRandomSpeed() {
    const speeds = [0.5, 0.75, 1.0, 1.25, 1.5, 1.75, 2.0]; // Modify this array
    return speeds[Math.floor(Math.random() * speeds.length)];
}
```

### Start Position Range
Edit the `getRandomStartPosition()` function to change the range:
```javascript
function getRandomStartPosition(duration) {
    const maxStart = duration * 0.3; // Change 0.3 to adjust (0.3 = 30%)
    return Math.floor(Math.random() * maxStart);
}
```

### Styling
The CSS is embedded in the HTML file - customize colors, sizes, and animations in the `<style>` section.

## 🔒 Privacy & Security

- No data is collected or stored
- No external analytics or tracking
- All processing happens in your browser
- Direct communication with YouTube API only

## 📝 License

This tool is provided as-is for educational and personal use.

## 🤝 Contributing

Feel free to fork and enhance this tool. Some ideas for improvements:
- Add manual speed controls
- Add duration range selector
- Add shuffle mode for playlists
- Add watch time tracker
- Add option to exclude certain speeds
- Add keyboard shortcuts

## ⚠️ Notes

- Requires active internet connection
- YouTube video must be embeddable (some videos restrict embedding)
- Playback speed is limited by YouTube's capabilities
- Some browsers may have autoplay restrictions

## 🎓 Use Cases

- **Study/Learning**: Loop educational videos with varied speeds for better retention
- **Music Practice**: Loop songs at different speeds for instrument practice
- **Language Learning**: Hear pronunciation at various speeds
- **Entertainment**: Create unique viewing experiences
- **Testing**: Test video player implementations
