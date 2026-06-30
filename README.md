# Steam Library Compare

Steam Library Compare is a Windows app used to scan, filter, share, and compare Steam Libraries with others.

SLC was created to solve a very specific problem with finding games to play together with friends on Steam: Taking family sharing into account. When selecting "Find Games To Play Together" for someone on your friends list, Steam only reports games the other user owns, and not games they also have access to through family sharing. If your friend had a game in their family share but not in their library, "Find Games To Play Together" would not list it as a game you both have access to. SLC is a solution to this problem, reporting the full list of all games you own and allowing you to export that list and share it to friends, letting them see your true complete library of playable games, filter games you both have access to, filter categories, and more. It even works with more than one friend's libraries at the same time, too.

This app can also be used to gather information on prices, game modes (Online, PvP, co-op, etc) for the games you have access to as well.

Steam Library Compare is an independent, unofficial application and is not affiliated with, endorsed by, or sponsored by Valve Corporation.

SLC is Created and maintained by **risuterra**.

---

## Requirements

The installer requires:

- Windows 10 or Windows 11, 64-bit
- .NET 10 Desktop Runtime x64
- Steam installed locally on your machine
- Internet access for:
  - Steam metadata downloads
  - Regional price metadata downloads
  - Steam Web API operations
  - App update checks
- A Steam Web API key for features that require Steam account or Web API access

If the required .NET 10 Desktop Runtime is not installed, the installer will direct you to the official Microsoft download page.

## Installation

1. Download the latest installer from the GitHub Releases page.
2. Run the installer.
3. Install the required .NET 10 Desktop Runtime x64 if prompted.
4. Complete the installation.
5. Launch Steam Library Compare from:
   - The Start Menu
   - The optional desktop shortcut
   - The installation folder

The default installation path is: `C:\Program Files\SteamLibraryCompare`

## Persistent Data Location

Steam Library Compare stores settings and user data under: `%LocalAppData%\SteamLibraryCompare`

This may include:

- Application settings
- Saved libraries
- Metadata caches
- Regional price caches
- Language-specific metadata
- Game catalog data
- Update-check timestamps

Because this data is stored outside the installation folder, it can persist across updates, reinstalls, and normal uninstall operations.

Uninstalling the application does not immediately remove your saved settings, libraries, metadata cache, or other persistent user data.

## Main Features

Steam Library Compare can:

- Scan locally available Steam library records
- Save discovered libraries for later use
- Load multiple saved or imported libraries
- Compare shared games across multiple libraries
- Import library files
- Export filtered library results
- Search result data across multiple fields
- Filter by:
  - Expected size
  - Price
  - Genres
  - Play modes and supported features
- Download localized Steam metadata
- Download prices for a selected Steam store region
- Cache metadata separately by language and region
- Switch between supported interface languages
- Use light or dark mode
- Check for newer GitHub releases

## Populating Your Library

Use **Scan Library** to search Steam files available on the current computer.

The local scanner may use data such as:

- Installed `appmanifest_*.acf` files
- Steam library cache records
- Cached game names from local Steam configuration files

This is useful when:

- You want to capture the games represented on the current computer
- You want to preserve a snapshot of a local Steam setup
- You want to compare multiple computers
- You want to compare your local library against a library shared by another person

Because scanning is based on files available locally, games with no local manifest, cache entry, or configuration record may not be discovered.

## Add a library from a file/code

Use **Add via file** or **Add via code** to import a library via supported file or code.

This is useful when:

- Someone sends you an exported library
- You are restoring a previously saved library
- You want to compare libraries across different computers
- You want to keep historical snapshots
- You want to compare current results against an older export

## Saved Libraries

The app separates libraries into saved and loaded groups.

Saved libraries are stored locally and can be reused in later sessions. They are not actively loaded into the Results list.

Saved libraries may be:

- Loaded
- Renamed
- Removed
- Exported

## Loaded libraries

Loaded libraries are currently active libraries in the Results list.

The Results list populates with only games shared by all actively loaded libraries. If a single library of games is loaded, it shows that entire library.

Use **Load All** or **Unload All** to quickly change which saved libraries are active.

## Exporting Libraries

Use **Export Library Results** to save the current filtered result set.

Exporting is useful for:

- Sharing a library with another user
- Creating a backup
- Saving a historical snapshot
- Moving library data to another computer
- Reusing a filtered subset
- Comparing results later

Depending on the selected export format, exported data may include:

- App IDs
- Game names
- Metadata
- Filter-relevant information
- Regional price information
- Library identity and contributor information

Keep exported files private if they contain information you do not want to share.

## Importing Libraries

Imported libraries can be loaded alongside local or saved libraries.

Typical uses include:

- Comparing libraries of multiple users
- Restoring a backup
- Comparing an old library snapshot with a current scan
- Sharing a curated list of games
- Reviewing the intersection between several exported libraries

When importing older data, metadata may be refreshed if it is missing, stale, or stored for a different language or region.

## Searching Results

The search box checks multiple visible fields and is not limited to just the Game name. Search also checks:

- App ID
- Expected size
- Play modes
- Displayed price

## Filtering Results

Use **Filters** to narrow the currently shared result set.

Filters include:

- Maximum size of installation
- Maximum price of game
- Genres
- Play modes / features
- Platform availability

Filters can be set to match "all" or "any" for filters where multiple options are selected.

## Steam Metadata

Steam Library Compare can download metadata such as:

- Localized game titles
- Expected storage size
- Genres
- Play modes
- Supported Steam features
- Store-page links
- Regional prices
- Currency information

Metadata is cached separately based on:

- Selected application language
- Selected Steam store region

A metadata cache is considered "recent" for approximately seven days and will warn the user if they're trying to refresh data that was recently obtained.

When changing the selected language or store region, the app checks whether a complete recent cache exists for that exact combination and tries to load that data, if it exists. If a complete cache is unavailable, the app may ask you to refresh metadata.

### Refresh All

This option downloads metadata again for **all** available games in the current result set or library set.

Use this when:

- You suspect cached data is incomplete
- Steam metadata has changed
- You want to replace all cached values
- You changed your language/store region and want a complete clean refresh

### Refresh Needed

Downloads only metadata that is:

- Missing
- Older than the cache lifetime
- Unavailable for the current language/store region

This is usually faster and is useful after an interrupted refresh.

Steam request limits and practical pacing may mean that only around 250 games can be updated per five minutes. This means that if you had for example 800 games, it would take roughly 15 minutes for the app to download metadata. Refreshed data is considered "recent" for up to a week without need for a new refresh.

## Steam Web API Key

Some Steam-related operations may require a Steam Web API key.

You can request a personal key from Steam's official Web API key page.

When registering a personal key, you can use `localhost` as the domain name if you do not operate a public website.

Never share your API key with anyone else.

SLC does not need your Steam password at any time. SLC does not access or report any private or confidential account information at any time.

## Languages

SLC supports external language packs. Missing translations fall back to English.

Metadata language and interface language are coordinated so game titles and metadata do not intentionally mix between unrelated language caches.

*Languages other than English may not be fully accurate. Please report any fixes for translations to help improve SLC!*

## Store Region and Currency

The selected store region controls which regional Steam prices are downloaded and displayed.

Changing the language does not change the underlying currency or store region selection.

Changing the store region may require a separate metadata refresh because price data is cached by region.

## Updates

SLC may check GitHub Releases for a newer stable version on startup.

When an update is found, SLC may display an offer to open the release page for the update. SLC does not automatically download or execute any installers.

Update installation is performed by downloading and running the newer installer from the official GitHub Releases page.

Settings and saved data are stored locally and should continue to work after an update.

## Uninstallation

Use either:

- Windows Settings > Apps
- The uninstaller in the installation folder
- The Start Menu uninstall entry, if present

The standard uninstaller removes files installed under `C:\Program Files\SteamLibraryCompare`. It does not normally remove any data stored at `%LocalAppData%\SteamLibraryCompare`.

To completely reset the SLC and all saved settings, uninstall it and manually delete the LocalAppData folder.

## Privacy

Steam Library Compare does not operate an analytics service.

The application may communicate directly with Steam services and GitHub for:

- Steam metadata
- Regional pricing
- Steam Web API operations
- Update checks

Saved libraries, settings, and cached metadata are stored locally unless you manually export or share them.

## Valve and Steam Disclaimer

Steam Library Compare is an independent, unofficial application and is not affiliated with, endorsed by, or sponsored by Valve Corporation.

## License

A separate copy of this license is also included as: `LICENSES\SteamLibraryCompare-LICENSE.txt`

Copyright © 2026 Risuterra. All rights reserved.

Permission is granted to download and use unmodified official releases of Steam Library Compare for personal, non-commercial use.

The software, source code, installer, documentation, artwork, and other included materials may not be copied, modified, redistributed, sublicensed, sold, or incorporated into another product without prior written permission from the copyright holder, except where a separate third-party license expressly permits otherwise.

Steam Library Compare is an independent, unofficial application and is not affiliated with, endorsed by, or sponsored by Valve Corporation.

Steam and the Steam logo are trademarks and/or registered trademarks of Valve Corporation in the United States and/or other countries.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE, AND NON-INFRINGEMENT. IN NO EVENT SHALL THE COPYRIGHT HOLDER BE LIABLE FOR ANY CLAIM, DAMAGES, OR OTHER LIABILITY ARISING FROM, OUT OF, OR IN CONNECTION WITH THE SOFTWARE OR THE USE OF THE SOFTWARE.