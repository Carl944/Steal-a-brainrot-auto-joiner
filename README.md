# Steal a Brainrot Auto Joiner

A Roblox script for automatically joining high-income servers in "Steal a Brainrot" by Sammy.

## 🎯 Features

### Core Functionality
- ✅ **Smart Server Filtering** - Only shows Steal-a-Brainrot servers (no ghost servers!)
- ✅ **Automatic Server Scanning** - Finds high-income public servers
- ✅ **Income-Based Joining** - Joins servers with income ≥ threshold (default 100M/s)
- ✅ **ESP System** - Highlights the highest value Brainrot on the server
- ✅ **Modern UI** - Neon black theme with purple accents

### Advanced Filtering (NEW!)
- 🚫 **Ghost Server Prevention** - Validates servers are running the correct game
- 👥 **Player Count Filter** - Avoid crowded servers (configurable max player count)
- 🧠 **Brainrot Filtering** - Whitelist/blacklist specific brainrot types
- ⚡ **Universe ID Validation** - Ensures servers match Steal-a-Brainrot
- 🎯 **Multi-Filter System** - Combines all filters for optimal results

## 🚀 Quick Start

1. **Get an Executor**: Use a Roblox script executor (e.g., Synapse, KRNL, etc.)
2. **Copy the Script**: Copy the entire `Auto-joiner` file
3. **Execute in Game**: Run the script while in Roblox
4. **Click the Brain Icon**: UI appears on the left side of screen
5. **Configure Settings**: Adjust income threshold and filters
6. **Start Auto-Joiner**: Click "Start Auto-Joiner" button

## 📋 Configuration

### Basic Settings

| Setting | Default | Description |
|---------|---------|-------------|
| Minimum Income | 100M/s | Only join servers with this income or higher |
| Max Player Count | 12 | Skip servers with more than this many players |
| Scan Interval | 30s | Time between server scans |
| Place ID | 109983668079237 | Steal a Brainrot official game ID |

### Advanced Filters

```lua
-- Filter by player count (avoid crowded servers)
Config.MaxPlayerCount = 8  -- Only join servers with < 8 players

-- Ignore servers with unknown brainrots
Config.IgnoreUnknown = true

-- Only join servers with specific brainrots (whitelist)
Config.BrainrotWhitelist = {"Sigma", "Grimace", "Gigachad"}

-- Never join servers with these brainrots (blacklist)
Config.BrainrotBlacklist = {"Ohio", "Beta", "Sus"}

-- Validate that servers are running Steal-a-Brainrot
Config.ValidateGameMatch = true
```

## 🎮 Usage

### UI Tabs

1. **Dashboard** - Status, statistics, and main toggle
2. **Settings** - Configure income threshold, scan interval, and player count
3. **Servers** - View all eligible servers with details
4. **ESP** - Toggle Brainrot ESP highlighting

### How to Use

1. Open the UI by clicking the brain emoji icon
2. Go to **Settings** tab to configure:
   - Minimum income threshold
   - Scan interval (seconds between scans)
   - Max player count (avoid full servers)
3. Return to **Dashboard** tab
4. Click "Start Auto-Joiner" (🔴 → 🟢)
5. Script automatically scans and joins best servers
6. Enable ESP in the ESP tab for in-game highlighting

### Recommended Workflow

```
1. Join Steal a Brainrot
2. Execute the Auto-joiner script
3. Click brain icon to open UI
4. Configure your desired settings
5. Start the auto-joiner
6. Script finds and joins high-income servers
7. ESP highlights the best brainrot to steal
```

## 🛡️ Server Filtering Explained

### Why Server Filtering Matters

Without proper filtering, you might:
- ❌ See servers from other games (ghost servers)
- ❌ Join full servers where you can't participate
- ❌ Waste time on low-value servers
- ❌ Join servers with undesirable brainrots

### How It Works

The auto-joiner uses **5-stage filtering**:

```
Stage 1: Fetch servers from Roblox API using Universe ID
         ↓
Stage 2: Validate server is from Steal-a-Brainrot
         ↓
Stage 3: Check if server is public and not full
         ↓
Stage 4: Verify income meets minimum threshold
         ↓
Stage 5: Validate brainrot names (whitelist/blacklist)
         ↓
Result: Only eligible servers shown and joined
```

### Filter Examples

**Conservative (High Quality)**
```lua
Config.MinimumIncome = 200000000  -- 200M/s
Config.MaxPlayerCount = 8
Config.BrainrotWhitelist = {"Sigma", "Grimace"}
```
→ Only high-income, low-player servers with specific brainrots

**Aggressive (More Opportunities)**
```lua
Config.MinimumIncome = 100000000  -- 100M/s
Config.MaxPlayerCount = 12
Config.BrainrotWhitelist = {}  -- Any brainrot
```
→ Any server meeting income threshold

**Blacklist Specific Types**
```lua
Config.MinimumIncome = 150000000
Config.BrainrotBlacklist = {"Ohio", "Beta"}
```
→ Good income but avoiding specific brainrots

## 📊 Statistics Tracking

The UI displays:
- **Servers Scanned**: Total servers checked
- **Eligible Servers**: Servers passing all filters
- **Current Income Threshold**: Your minimum income setting

## 🎨 ESP System

### Features
- Highlights **ONLY** the highest value brainrot on the server
- Neon pink/purple glow effect
- Billboard label with name and value
- Auto-updates every 2 seconds
- Toggle on/off via ESP tab

### Brainrot Types Detected
- Skibidi, Grimace, Cameraman
- Ohio, Rizz, Sigma, Gyatt
- Mewing, Fanum, Smurf Cat
- Rizz God, Sigma Male, Gigachad
- And more...

## 🔧 Troubleshooting

### No Servers Found
**Cause**: Filters too strict or API issues  
**Fix**: 
- Lower minimum income threshold
- Increase max player count
- Clear whitelist/blacklist
- Check console for errors

### Ghost Servers Appearing
**Cause**: Validation disabled or incorrect Place ID  
**Fix**:
- Verify `Config.ValidateGameMatch = true`
- Check `Config.PlaceId = 109983668079237`
- Update to latest script version

### Can't Join Servers
**Cause**: Server full or teleport error  
**Fix**:
- Lower `MaxPlayerCount` to avoid full servers
- Wait for scan to find new servers
- Check console for teleport errors

### ESP Not Working
**Cause**: ESP disabled or no brainrots found  
**Fix**:
- Enable ESP in ESP tab
- Verify you're in an active server
- Check that brainrots exist in workspace

## 📖 Advanced Topics

See [FILTERING_GUIDE.md](FILTERING_GUIDE.md) for detailed information on:
- Advanced configuration examples
- Best practices from similar auto joiners
- Technical implementation details
- API endpoints and validation
- Debugging and troubleshooting

## ⚠️ Important Notes

### Safety
- Use at your own risk
- May violate Roblox Terms of Service
- Risk of account suspension/ban
- Don't share account credentials
- Use responsibly

### Performance
- Don't run 24/7 (detection risk)
- Use reasonable scan intervals (30+ seconds)
- Don't join servers too rapidly
- Monitor for game updates

### Ethics
- Respect other players
- Follow game rules
- Don't exploit or abuse
- Use for intended purposes only

## 🔄 Updates

### Version 2.0 (Latest)
- ✅ Fixed ghost server issue
- ✅ Added comprehensive server filtering
- ✅ Added player count filtering
- ✅ Added brainrot whitelist/blacklist
- ✅ Improved Universe ID validation
- ✅ Enhanced error handling
- ✅ Added UI controls for new settings
- ✅ Better logging and notifications

### Version 1.0
- Initial release
- Basic auto-joining
- ESP system
- Simple UI

## 📝 Credits

**By**: Sammy (SpyderSammy)  
**Game**: Steal a Brainrot (Official)  
**Place ID**: 109983668079237

Inspired by best practices from:
- Chilli Hub Auto Joiner
- Nameless Hub
- Community feedback

## 📞 Support

For issues or improvements:
1. Read the documentation
2. Check console for errors
3. Verify configuration
4. Review [FILTERING_GUIDE.md](FILTERING_GUIDE.md)
5. Report bugs with details

---

**Disclaimer**: This script is provided as-is for educational purposes. Use at your own risk. The author is not responsible for any consequences of using this script, including but not limited to account bans, data loss, or any other damages.
