✨ Main Features
🚂 Automatic Minecart Spawning
Right-click on rails (Rail, Powered Rail, Detector Rail) with an empty hand
Minecart spawns automatically and player is instantly teleported into it
Does not work with Activator Rails
⚡ High-Speed Auto Movement
Minecart moves at maximum speed like in Terraria
No need for powered rails to be active for high speed
Movement direction follows player's facing direction
🗑️ Auto-Delete Minecarts
Minecarts are automatically deleted when players exit
Prevents minecart spam on servers
Configurable in config file
🌍 World Management
Disable plugin functionality in specific worlds
Configure through config.yml file
Perfect for multi-world servers
👤 Per-Player Controls
Each player can toggle functionality on/off for themselves
/togglecart command for personal settings
Settings persist during session
🔧 Full Configuration
Adjustable maximum speed settings
Toggle sound effects
Auto-delete configuration
Disabled worlds list
📝 Commands
Command Description Permission
/togglecart Toggle AutoMinecart functionality for yourself autominecart.use
🔐 Permissions
Permission Description Default
autominecart.use Allows players to use AutoMinecart true
autominecart.admin Admin permissions for AutoMinecart op

⚙️ Configuration (config.yml)
[code=YAML]# List of worlds where AutoMinecart should be disabled
disabled-worlds:
  - "example_disabled_world"

# Maximum speed for auto minecarts (0.1 = slow, 0.4 = fast, 0.6 = very fast)
max-speed: 0.4

# Whether to automatically delete minecarts when players exit them
delete-empty-carts: true

# Whether to play sound effects when spawning/riding minecarts
enable-sound-effects: true[/code]

🎮 How to Use
Hold an empty hand (no items in main hand)
Right-click on any rail (Rail, Powered Rail, or Detector Rail)
Minecart spawns and you're automatically teleported into it
Minecart moves automatically at high speed in your facing direction
Exit the minecart and it will be automatically deleted
⚠️ Important Notes
Powered rails must be active if the minecart travels over them (Minecraft limitation)
Avoid too many sharp corners as high speed may cause the minecart to fly off tracks
Only works with Rail, Powered Rail, and Detector Rail (Activator Rails are excluded)
Won't spawn multiple minecarts for the same player
🔧 Compatibility
Minecraft Version: 1.21.3 - 1.21.6
Server Software: Spigot, Paper (recommended)
Java Version: 17+
API: Spigot API 1.21.3
attachFull903553
