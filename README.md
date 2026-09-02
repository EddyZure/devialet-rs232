# devialet-rs232

# A Devialet Raspberry Pi Bridge

This bridge connects a Devialet Expert amplifier over RS-232 to MQTT and Home Assistant. It also provides a lightweight local web interface and JSON API.

## Features

- Bidirectional RS-232 communication with the Devialet amplifier
- MQTT status topics and command handling
- Automatic Home Assistant discovery
- Mobile-friendly local web interface
- JSON status and command API with live Server-Sent Events
- Automatic startup and recovery through systemd

## Repository contents

- `src/devialet_bridge.py` — the RS-232, MQTT, Home Assistant, web and API bridge
- `src/devialet_web_assets/` — images used by the web interface
- `systemd/devialet-bridge.service` — systemd service definition
- `.env.example` — configuration template without real credentials
- `scripts/install.sh` — installation and update script for Raspberry Pi OS
- `scripts/backup.sh` — public export and private configuration backup
- `scripts/restore.sh` — private-backup restore script
- `scripts/check-secrets.sh` — basic check for secret files before publishing

Historical development files are intentionally excluded. The repository contains only the latest working version required for deployment.

## Requirements

- Raspberry Pi OS with systemd
- Python 3.7 or newer
- RS-232/USB adapter, normally available as `/dev/ttyUSB0`
- Reachable MQTT broker
- Internet access during initial installation for the Python dependencies

The application uses pure-Python dependencies and does not require a build toolchain.
