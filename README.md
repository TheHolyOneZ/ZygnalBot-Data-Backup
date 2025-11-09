# ZygnalBot-Data-Backup
The Data Backup Extension allows you to create backups of your bot's data folder and transfer configurations between deployments. This is essential for preserving user settings, configurations, and cached data when moving between hosting providers or updating your bot deployment.
> 💡 **Built for the Zygnal Ecosystem — to download and use this extension, you must be part of the Zygnal Ecosystem.**  
> This extension (cog) is part of the **Zygnal Ecosystem** and is only available through its supported platforms.  
> You can use it with:  
> - The **[Discord Bot Framework](https://github.com/TheHolyOneZ/discord-bot-framework)** — ideal for developers who want full control and flexibility *(includes an integrated extension marketplace)*, or  
> - The **[ZygnalBot](https://zygnalbot.de)** — a prebuilt, plug-and-play Discord bot *(also includes an integrated extension marketplace)*.  
>
> Browse and install extensions at [zygnalbot.com/extension](https://zygnalbot.com/extension).  
> For help or community discussions, join us on Discord: [discord.gg/sgZnXca5ts](https://discord.gg/sgZnXca5ts)
# ZygnalBot Data Backup Extension

## Overview
The Data Backup Extension allows you to create backups of your bot's data folder and transfer configurations between deployments. This is essential for preserving user settings, configurations, and cached data when moving between hosting providers or updating your bot deployment.

## Installation

### Step 1: Install the Extension
1. Download the `data_backup_extension.py` file
2. Place it in your `Extensions` folder
3. Restart your bot

The extension will automatically load when the bot starts.

## Usage

### Available Commands

#### `!backup_data`
- **Aliases:** `!download_data`, `!export_data`
- **Permission Required:** Administrator
- **Description:** Creates a zip backup of the entire data folder and sends it in the current channel

#### `!backup_info`
- **Permission Required:** None
- **Description:** Shows information about the data folder (size, file count, etc.)

## Complete Backup & Restore Process

### Creating a Backup

1. **Setup your bot systems first:**
   - Configure birthday system
   - Set up welcome messages
   - Configure moderation settings
   - Set up any other extensions and their settings

2. **Create the backup:**
   ```
   !backup_data
   ```

3. **Download the zip file:**
   - The bot will send a timestamped zip file (e.g., `data_backup_20250103_143022.zip`)
   - Download this file to your computer

### Restoring to New Deployment

1. **Extract the backup:**
   - Unzip the downloaded backup file
   - You'll see all your data files and folders

2. **Create data folder structure:**
   - Create a new folder called `data` in your project root
   - Drag and drop everything from the extracted zip into this `data` folder
   - Maintain the folder structure (JSON files, subfolders, etc.)

3. **Deploy to your repository:**
   - Upload the `data` folder to your ZygnalBot GitHub repository
   - Place it in the root directory alongside your bot files
   - If there's an existing `data` folder, replace it completely

4. **Deploy your bot:**
   - Your hosting provider will now use the pre-configured data folder
   - All your settings, user data, and configurations will be preserved

## Benefits

### Persistent Configuration
- **Hosting Provider Independence:** Even if your hosting provider deletes generated files, your configurations persist
- **Easy Migration:** Move between different hosting services without losing data
- **Backup Safety:** Regular backups prevent data loss

### What Gets Backed Up
- User configurations and settings
- Birthday system data
- Welcome message configurations
- Moderation settings
- Extension-specific data
- Cached information
- JSON configuration files
- Any other data stored in the data folder

## File Size Limitations

- **Discord Limit:** 25MB maximum file size
- **Large Backups:** If your data folder exceeds 25MB, the extension will notify you
- **Optimization:** Consider cleaning old cache files if backups become too large

## Example Workflow

```
1. Set up bot on hosting provider A
2. Configure all systems (birthday, welcome, etc.)
3. Run: !backup_data
4. Download: data_backup_XXXX_XXXX.zip
5. Extract zip contents
6. Create new "data" folder
7. Move extracted files into "data" folder
8. Upload "data" folder to GitHub repository
9. Deploy to hosting provider B
10. Bot starts with all previous configurations intact
```

## Troubleshooting

### Common Issues

**"Data folder not found"**
- The bot hasn't created a data folder yet
- Use the bot features first to generate data files

**"File too large to send"**
- Your data folder exceeds 25MB
- Clean up old cache files or contact support

**"Administrator permissions required"**
- Only server administrators can create backups
- This prevents unauthorized data access

### Best Practices

1. **Regular Backups:** Create backups before major changes
2. **Clean Data:** Periodically clean old cache files
3. **Test Deployments:** Verify backups work in test environments
4. **Version Control:** Keep your data folder in version control
5. **Documentation:** Document any custom configurations

## Important Note

**The Data folder is Global** - It contains **ALL** configurations including all guilds the bot is connected with and that have systems setup that use the data folder. This means one backup contains data for every server your bot operates in.
