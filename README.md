# ResHub - Image Hosting Repository

[中文文档](./README_CN.md) | English

## Overview

ResHub is a personal image hosting repository designed to store and serve images for blogs, documentation, and other purposes using GitHub as the backend storage.

## How to Use on Mobile Devices

### Option 1: PicGo Mobile Alternative - PicList (Recommended)

Since PicGo desktop doesn't have an official mobile app, you can use **PicList** which supports both desktop and mobile platforms.

#### For Android:
1. Download PicList from [GitHub Releases](https://github.com/Kuingsmile/PicList)
2. Install the APK on your Android device
3. Configure GitHub as your upload destination:
   - **Token**: Your GitHub Personal Access Token (with `repo` scope)
   - **Repository**: `GameDevTurbo/ResHub`
   - **Branch**: `main`
   - **Path**: Choose your folder (e.g., `img/`, `TyproaPic/`, etc.)
   - **Custom Domain**: `https://raw.githubusercontent.com/GameDevTurbo/ResHub/main/`

#### For iOS:
Due to iOS restrictions, consider using Option 2 or Option 3 below.

### Option 2: GitHub Mobile App

1. Install the official GitHub app on your mobile device
2. Navigate to the ResHub repository
3. Browse to the folder where you want to upload images
4. Tap the "+" button and select "Upload files"
5. Choose images from your gallery or camera
6. Add a commit message and commit directly to main branch

**Pros**: Official GitHub app, secure and reliable  
**Cons**: No image compression, no batch operations, less convenient

### Option 3: Termux + Git (Android Only)

For advanced users on Android:

1. Install [Termux](https://f-droid.org/packages/com.termux/) from F-Droid
2. Set up Git:
   ```bash
   pkg install git
   git config --global user.name "Your Name"
   git config --global user.email "your.email@example.com"
   ```
3. Clone the repository:
   ```bash
   cd ~/storage/shared
   git clone https://github.com/GameDevTurbo/ResHub.git
   cd ResHub
   ```
4. Upload images:
   ```bash
   cp ~/storage/dcim/Camera/photo.jpg ./img/
   git add .
   git commit -m "Upload photo"
   git push
   ```

**Pros**: Full Git functionality, scriptable  
**Cons**: Requires technical knowledge, terminal-based

### Option 4: Third-Party Image Hosting Apps

Several mobile apps support uploading to GitHub:

- **uPic** (iOS): Supports GitHub as a backend
- **PicGo-Core** based apps: Search for community-developed mobile versions

## Setting Up GitHub Personal Access Token

To use any of the above methods (except GitHub Mobile App), you'll need a Personal Access Token:

1. Go to [GitHub Settings > Developer settings > Personal access tokens](https://github.com/settings/tokens)
2. Click "Generate new token (classic)"
3. Give it a name (e.g., "ResHub Mobile Upload")
4. Select the `repo` scope (full control of private repositories)
5. Click "Generate token"
6. **Important**: Copy the token immediately - you won't be able to see it again!

## Repository Structure

```
ResHub/
├── TyproaPic/     # Images uploaded via Typora
├── img/           # General images
├── picG/          # PicGo uploads
└── picGoGoGo/     # Additional images
```

## Getting Image URLs

After uploading, you can access your images using:

### Raw URL (Direct Access):
```
https://raw.githubusercontent.com/GameDevTurbo/ResHub/main/[folder]/[filename]
```

### HTML Image Tag:
```html
<img src="https://raw.githubusercontent.com/GameDevTurbo/ResHub/main/img/example.png" alt="Description">
```

### Markdown:
```markdown
![Description](https://raw.githubusercontent.com/GameDevTurbo/ResHub/main/img/example.png)
```

## Tips for Mobile Usage

1. **Image Compression**: Compress images before uploading to save bandwidth and storage
2. **Organized Folders**: Use consistent folder names for better organization
3. **Commit Messages**: Use descriptive commit messages for easier tracking
4. **CDN Alternative**: Consider using jsDelivr for faster image loading:
   ```
   https://cdn.jsdelivr.net/gh/GameDevTurbo/ResHub@main/img/example.png
   ```

## Troubleshooting

### Upload Failed
- Check your GitHub token permissions
- Verify repository name is correct
- Ensure you have write access to the repository

### Images Not Loading
- GitHub raw URLs might be slow in some regions
- Try using jsDelivr CDN as an alternative
- Check if the image path is correct

### Token Expired
- GitHub tokens don't expire unless you set an expiration date
- If expired, generate a new token following the steps above

## License

This repository is for personal use. All images remain the property of their respective owners.
