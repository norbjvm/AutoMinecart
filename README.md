# AutoMinecart

[![Minecraft Version](https://img.shields.io/badge/Minecraft-1.21.3--1.21.6-brightgreen.svg)](https://www.minecraft.net/)
[![Spigot API](https://img.shields.io/badge/Spigot%20API-1.21.3-orange.svg)](https://www.spigotmc.org/)
[![Java Version](https://img.shields.io/badge/Java-17%2B-blue.svg)](https://adoptium.net/)
[![License](https://img.shields.io/badge/License-Open%20Source-green.svg)](LICENSE)


## 🚀 Features

- ✅ **Instant Minecart Spawning**: Right-click any rail with an empty hand to spawn and enter a minecart
- ✅ **Terraria-Style Movement**: Automatic high-speed travel similar to Terraria minecarts
- ✅ **Auto-Cleanup**: Minecarts are automatically deleted when players exit
- ✅ **World Management**: Configure disabled worlds in config.yml
- ✅ **Permission System**: Use `autominecart.use` permission for access control
- ✅ **Player Toggle**: `/togglecart` command to enable/disable functionality per player
- ✅ **Sound Effects**: Configurable audio feedback
- ✅ **Lightweight**: Minimal server performance impact

## 📦 Installation

### Requirements
- **Minecraft Server**: Spigot or Paper 1.21.3-1.21.6
- **Java**: Version 17 or higher
- **Permissions Plugin**: Optional (for advanced permission management)

### Installation Steps

1. **Download** the latest `AutoMinecart-x.x.x.jar` from [Releases](../../releases)
2. **Place** the JAR file in your server's `plugins` folder
3. **Restart** your server
4. **Configure** the plugin in `plugins/AutoMinecart/config.yml` (optional)

## 🎮 How to Use

### Basic Usage

1. **Empty your main hand** (don't hold any items)
2. **Right-click on a rail** (Rail, Powered Rail, or Detector Rail)
3. **You'll be teleported** into an automatically spawned minecart
4. **The minecart moves automatically** at high speed in your facing direction
5. **Exit the minecart** and it will be automatically deleted

### Supported Rails

| Rail Type | Supported | Notes |
|-----------|-----------|-------|
| Rail | ✅ | Works perfectly |
| Powered Rail | ✅ | Must be powered if cart passes over |
| Detector Rail | ✅ | Works perfectly |
| Activator Rail | ❌ | Excluded by design |

## ⚙️ Configuration

### config.yml

```yaml
# AutoMinecart Configuration File
# Author: LythNorb

# List of worlds where AutoMinecart should be disabled
# Example: ["world_nether", "creative_world"]
disabled-worlds:
  - "example_disabled_world"

# Maximum speed for auto minecarts (0.1 = slow, 0.4 = fast, 0.6 = very fast)
# Note: Values too high may cause minecarts to fly off tracks on corners
max-speed: 0.4

# Whether to automatically delete minecarts when players exit them
delete-empty-carts: true

# Whether to play sound effects when spawning/riding minecarts
enable-sound-effects: true
```

### Configuration Options

| Option | Type | Default | Description |
|--------|------|---------|-------------|
| `disabled-worlds` | List | `["example_disabled_world"]` | Worlds where the plugin is disabled |
| `max-speed` | Double | `0.4` | Maximum minecart speed (0.1-0.6 recommended) |
| `delete-empty-carts` | Boolean | `true` | Auto-delete minecarts when empty |
| `enable-sound-effects` | Boolean | `true` | Play sound effects |

## 📝 Commands

| Command | Description | Permission | Usage |
|---------|-------------|------------|-------|
| `/togglecart` | Toggle AutoMinecart for yourself | `autominecart.use` | `/togglecart` |

### Command Examples

```
/togglecart
# Output: AutoMinecart functionality ENABLED! Right-click rails with an empty hand to spawn minecarts.

/togglecart
# Output: AutoMinecart functionality DISABLED! You will no longer spawn minecarts when right-clicking rails.
```

## 🔐 Permissions

| Permission | Description | Default | Children |
|------------|-------------|---------|----------|
| `autominecart.use` | Allows using the AutoMinecart plugin | `true` | - |
| `autominecart.admin` | Admin permissions for AutoMinecart | `op` | `autominecart.use` |

### Permission Examples

**LuckPerms:**
```
/lp group default permission set autominecart.use true
/lp group admin permission set autominecart.admin true
```

**PermissionsEx:**
```
/pex group default add autominecart.use
/pex group admin add autominecart.admin
```

## ⚠️ Important Notes

### Performance Considerations
- **Powered Rails**: Must be powered when minecarts pass over them (Minecraft limitation)
- **Sharp Corners**: Too many close corners may cause minecarts to derail due to high speed
- **Entity Cleanup**: Plugin automatically prevents minecart spam through auto-deletion

### Best Practices
- **Track Design**: Build gentle curves instead of sharp 90° turns
- **Powered Rails**: Ensure powered rails are properly activated
- **World Configuration**: Disable in creative or build worlds if needed

## 🛠️ Development

### Building from Source

```bash
# Clone the repository
git clone https://github.com/LythNorb/AutoMinecart.git
cd AutoMinecart

# Build with Maven
mvn clean package

# The compiled JAR will be in target/AutoMinecart-x.x.x.jar
```

### Development Setup

1. **Clone** the repository
2. **Import** into your IDE (IntelliJ IDEA recommended)
3. **Configure** Maven project
4. **Set up** Spigot API dependency
5. **Build** and test on local server

### API Usage

```java
// Check if player has AutoMinecart enabled
Player player = ...;
AutoMinecart plugin = AutoMinecart.getInstance();
boolean enabled = plugin.getPlayerDataManager().isEnabledForPlayer(player);

// Toggle AutoMinecart for player
boolean newState = plugin.getPlayerDataManager().togglePlayer(player);
```

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guidelines](CONTRIBUTING.md) for details.

### Ways to Contribute
- 🐛 **Bug Reports**: Report issues via GitHub Issues
- 💡 **Feature Requests**: Suggest new features
- 🔧 **Code Contributions**: Submit pull requests
- 📚 **Documentation**: Improve documentation
- 🌐 **Translations**: Help translate the plugin

## 📊 Compatibility

### Tested Versions

| Minecraft Version | Spigot | Paper | Status |
|-------------------|--------|-------|--------|
| 1.21.6 | ✅ | ✅ | Fully Compatible |
| 1.21.5 | ✅ | ✅ | Fully Compatible |
| 1.21.4 | ✅ | ✅ | Fully Compatible |
| 1.21.3 | ✅ | ✅ | Fully Compatible |

### Server Software

- **Spigot**: Full compatibility
- **Paper**: Full compatibility (recommended)
- **Purpur**: Should work (untested)
- **Bukkit**: Not supported

## 🐛 Troubleshooting

### Common Issues

**Q: Minecarts don't spawn when I right-click rails**
- A: Ensure your main hand is empty and you have the `autominecart.use` permission

**Q: Minecarts fly off tracks at corners**
- A: Reduce the `max-speed` value in config.yml or build gentler curves

**Q: Plugin doesn't work in my world**
- A: Check if your world is listed in `disabled-worlds` in config.yml

**Q: Sound effects don't play**
- A: Enable `enable-sound-effects: true` in config.yml

### Debug Steps

1. Check server console for errors
2. Verify plugin is loaded: `/plugins`
3. Check permissions: `/lp user <player> info`
4. Validate configuration file syntax
5. Test in different worlds

## 📋 Changelog

### Version 1.0.0
- ✨ Initial release
- ✅ Basic minecart spawning functionality
- ✅ Auto-movement system
- ✅ Configuration system
- ✅ Permission system
- ✅ Player toggle command


*If you enjoy this plugin, please consider leaving a ⭐ star on GitHub and a positive review on SpigotMC!* 
