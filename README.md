# Live Watch — Documentation

Live Watch is an Android TV / Google TV IPTV player built entirely in Jetpack
Compose (TV Material 3), with phone/tablet support for testing. It loads live-TV
playlists (M3U/M3U8, the free iptv-org catalog, or Xtream Codes accounts), plays
them with Media3/ExoPlayer, and adds the niceties expected of a 10-foot living-room
app: a focus-driven browse grid, search, an EPG guide, parental controls, an
on-disk cache, and an app-scoped integrated VPN.

## At a glance

- **Package root:** `com.extremex.livewatch`
- **Min / target SDK:** 33 / 36 · **Language:** Kotlin · **UI:** Compose + `androidx.tv:tv-material`
- **Player:** AndroidX Media3 (ExoPlayer) — HLS, DASH, progressive
- **Persistence:** Jetpack DataStore (Preferences) + a JSON file cache in `filesDir`
- **DI:** manual `AppContainer` (no Hilt/Dagger)
- **VPN:** WireGuard (`wireguard-android`, GPLv3) in-app + a vendored ics-openvpn
  engine (skeleton AAR) for anonymous RiseupVPN — both **app-scoped** (only
  LiveWatch's traffic is tunneled)

> The `ics-openvpn/` directory at the repo root is the **vendored upstream
> ics-openvpn source** used to build the skeleton AAR. It is a third-party
> dependency, not LiveWatch application code, and is intentionally not documented
> here beyond its role in the VPN feature.
