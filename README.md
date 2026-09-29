<div align="center">
  <h1 align="center">KitsuneLab©</h1>
  <h3 align="center">K4 - Damage Info</h3>
  <a align="center">A SwiftlyS2 plugin for Counter-Strike 2 that displays damage information to players. Shows real-time center screen damage indicators, console damage logs, and round-end damage summaries.</a>
</div>

<p align="center">
  <img src="https://img.shields.io/badge/build-passing-brightgreen" alt="Build Status">
  <img src="https://img.shields.io/github/downloads/Shmitzas/K4-DamageInfo-Upkeep/total?style=flat&logo=github&cacheSeconds=3600" alt="Downloads">
  <img src="https://img.shields.io/github/stars/Shmitzas/K4-DamageInfo-Upkeep?style=flat&logo=github&cacheSeconds=3600" alt="Stars">
  <img src="https://img.shields.io/github/license/Shmitzas/K4-DamageInfo-Upkeep" alt="License">
</p>

# Important notice!
> [!IMPORTANT]  
> [K4ryuu](https://github.com/K4ryuu) is the creator of this plugin.<br>
> Since he is no longer maintaining his CS2 plugins, I forked some of them and maintain them ONLY FOR BUG FIXES!

---

### Dependencies

To use this server addon, you'll need the following dependencies installed:

- [**SwiftlyS2**](https://github.com/swiftly-solution/swiftlys2): SwiftlyS2 is a server plugin framework for Counter-Strike 2

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- INSTALLATION -->

## Installation

1. Install [SwiftlyS2](https://github.com/swiftly-solution/swiftlys2) on your server
2. [Download the latest release](https://github.com/shmitzas/K4-DamageInfo-Upkeep/releases/latest)
3. Extract to your server's `swiftlys2/plugins/` directory

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- CONFIGURATION -->

## Configuration

### Basic Settings

| Option              | Description                                             | Default |
| ------------------- | ------------------------------------------------------- | ------- |
| `RoundEndSummary`   | Show damage summary at round end                        | `true`  |
| `AllowDeathPrint`   | Allow damage summary to be shown on death               | `true`  |
| `ShowOnlyKiller`    | Show only killer in round end summary                   | `false` |
| `ShowFriendlyFire`  | Show friendly fire damage in summary                    | `false` |
| `ShowAllDamages`    | Show all damages from all players                       | `false` |
| `CenterDamageInfo`  | Show center damage info on hit                          | `true`  |
| `CenterDamageMode`  | Center damage display mode: `1` = HTML, `2` = Alert     | `1`     |
| `ConsoleDamageInfo` | Show console damage info on hit                         | `true`  |
| `FFAMode`           | Free-for-all mode (show damage to teammates)            | `false` |
| `NoRoundsMode`      | No rounds mode - clear damage on death instead of round | `false` |
| `CenterInfoTimeout` | Timeout for center damage info display (seconds)        | `3`     |

### Permission Settings

| Option                                 | Description                                | Default | Permission Required     |
| -------------------------------------- | ------------------------------------------ | ------- | ----------------------- |
| `Permissions.ConsoleRequirePermission` | Require permission for console damage info | `false` | `k4.damageinfo.console` |
| `Permissions.CenterRequirePermission`  | Require permission for center damage info  | `false` | `k4.damageinfo.center`  |
| `Permissions.SummaryRequirePermission` | Require permission for chat damage summary | `false` | `k4.damageinfo.summary` |

### Permission Examples

**Config (`k4-damageinfo.jsonc`):**

```jsonc
{
  "K4DamageInfo": {
    "CenterDamageInfo": true,
    "ConsoleDamageInfo": true,
    "Permissions": {
      "ConsoleRequirePermission": true, // Only players with k4.damageinfo.console permission
      "CenterRequirePermission": false, // Everyone can see center damage
      "SummaryRequirePermission": false, // Everyone can see death/round summary
    },
  },
}
```

**Permissions (`admins.json`):**

```json
{
  "76561234": {
    "permissions": ["k4.damageinfo.*"] // All damage info permissions
  },
  "76565678": {
    "permissions": ["k4.damageinfo.console", "k4.damageinfo.center"]
  }
}
```

**Permission Flags:**

- `k4.damageinfo.console` - See console damage information
- `k4.damageinfo.center` - See center screen damage (HTML/Alert)
- `k4.damageinfo.summary` - See chat damage summary on death/round end
- `k4.damageinfo.*` - Wildcard for all damage info permissions

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- LICENSE -->

## License

Distributed under the GPL-3.0 License. See [`LICENSE.md`](LICENSE.md) for more information.

<p align="right">(<a href="#readme-top">back to top</a>)</p>
