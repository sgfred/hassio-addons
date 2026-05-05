# Homebridge - Home Assistant Add-on

## About

[Homebridge](https://homebridge.io) lets you integrate smart home devices that don't support HomeKit natively. This add-on runs Homebridge directly inside Home Assistant.

---

## Installation

1. Go to **Settings → Add-ons → Add-on Store**
2. Click the **⋮** menu → **Repositories**, and add this repository URL
3. Find **Homebridge** and click **Install**
4. Start the add-on
5. Open the **Web UI** (port `8581`)
6. Default login: `admin` / `admin` — **change this immediately!**

---

## First Setup

After starting the add-on, open the Web UI at `http://homeassistant.local:8581`.

### Add to Apple Home

1. Open the **Home** app on your iPhone/iPad
2. Tap **+** → **Add Accessory**
3. Tap **More options** → select **Homebridge**
4. Enter the PIN shown in the Web UI (default: `031-45-154`)

---

## Configuration

| Option | Description | Default |
|--------|-------------|---------|
| `log_level` | Verbosity: `trace`, `debug`, `info`, `warn`, `error` | `info` |

### Example add-on config

```yaml
log_level: info
```

---

## Plugins

Install plugins directly from the Homebridge Web UI under **Plugins** tab.

Popular plugins:
- `homebridge-tuya` — Tuya/Smart Life devices
- `homebridge-broadlink-rm` — Broadlink IR blasters
- `homebridge-ring` — Ring doorbells & cameras
- `homebridge-nest` — Nest thermostats

---

## Persistent Storage

All Homebridge data (config, plugins, certificates) is stored in the add-on's `/homebridge` volume, which maps to:

```
/addon_configs/<addon_slug>/homebridge/
```

Your data persists across restarts and updates.

---

## Network

This add-on uses **host network mode**, which is required for:
- HomeKit device discovery (mDNS/Bonjour)
- Proper pairing with Apple devices

---

## Troubleshooting

### HomeKit can't find Homebridge
- Make sure your HA device and Apple device are on the **same network**
- Restart the add-on and try pairing again
- Check that port `51826` (HomeKit bridge) is not blocked by a firewall

### Resetting the pairing
In the Web UI: **Settings → Homebridge Settings → Reset Homebridge**

### Logs
Go to the add-on page in HA and click the **Log** tab for real-time logs.
