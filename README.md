# Modrinth Pack Version Updater

A web-based tool to help manage updating Modrinth modpack (.mrpack) files to different Minecraft versions. This tool analyzes your modpack and checks which mods have compatible versions for your target Minecraft version.

## ⚠️ Quality Notice

This project has been "vibe coded" - prioritizing functionality over code maintainability. While it works well for its intended purpose, the codebase may not follow best practices for long-term maintenance.

## Features

- 🔍 **Version Compatibility Checking**: Upload a .mrpack file and check which mods are available for a target Minecraft version
- 🎯 **Multi-Loader Support**: Supports Fabric, Quilt, Forge, and NeoForge modloaders
- 📦 **Automatic Pack Building**: Generates updated .mrpack files with compatible mod versions
- 🏗️ **Special Carpet Handling**: Enhanced support for Fabric Carpet mod with GitHub fallback
- 📊 **Detailed Reports**: Shows availability status, version numbers, and download information
- 🎨 **Category Support**: Handles mods, resource packs, and shader packs separately

## How It Works

1. **Upload**: Drop your existing .mrpack file into the tool
2. **Configure**: Select your target Minecraft version and modloader
3. **Analyze**: The tool checks Modrinth API for compatible versions of each mod
4. **Review**: See which mods have updates available and which don't
5. **Build**: Generate a new .mrpack with all available updates

## Special Features

### Fabric Carpet Support
The tool includes special handling for Fabric Carpet mod:
- Falls back to GitHub releases when Modrinth doesn't have the version
- Automatically matches version patterns for better compatibility
- Supports both stable and prerelease versions

### Smart Version Selection
- Prioritizes release versions over beta/alpha
- Sorts by publication date for the most recent compatible version
- Maintains original file metadata for proper pack building

## Usage

1. Open `index.html` in a web browser
2. Click "Choose File" and select your .mrpack file
3. Select your target Minecraft version from the dropdown
4. Choose your modloader (Fabric, Quilt, Forge, NeoForge)
5. Click "Check" to analyze compatibility
6. Review the results in the generated tables
7. Click "Build updated .mrpack" to download an updated pack

## File Structure

```
├── index.html              # Main application (HTML + CSS + JavaScript)
├── jszip-dist/             # JSZip library for handling .mrpack files
│   ├── jszip.js
│   └── jszip.min.js
├── host.sh                 # Local development server script
├── LICENSE                 # MIT License
├── README.md               # This file
└── .gitignore              # Git ignore file
```

## Development

To run locally:

```bash
# Simple HTTP server (if you have host.sh)
./host.sh

# Or use Python
python3 -m http.server 8000

# Or use Node.js
npx serve .
```

Then open `http://localhost:8000` in your browser.

## API Dependencies

This tool relies on the following APIs:
- **Modrinth API v2**: For mod version and compatibility checking
- **GitHub API**: Fallback for Fabric Carpet mod releases
- **Minecraft Version Manifest**: For loading available MC versions

## Limitations

- ⚠️ **Code Quality**: Prioritizes functionality over maintainability
- 🌐 **Client-Side Only**: All processing happens in the browser
- 📡 **API Rate Limits**: May hit rate limits with very large modpacks
- 🔄 **No Automatic Dependencies**: Doesn't automatically resolve mod dependencies
- 📱 **Limited Mobile Support**: Best used on desktop browsers

## Contributing

While contributions are welcome, please note that this is a "vibe coded" project. The codebase prioritizes quick functionality over clean architecture. Consider this when making contributions.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

### Third-Party Licenses

- **JSZip**: Dual licensed under MIT/GPL v3 (this project uses the MIT license)

## Acknowledgments

- Built for the Minecraft modding community
- Uses the excellent Modrinth API for mod data
- Special thanks to the Fabric Carpet team for their GitHub releases
- Powered by JSZip for .mrpack file handling

---

**Note**: This tool is not affiliated with Modrinth or Minecraft. It's a community-created utility to help with modpack management.