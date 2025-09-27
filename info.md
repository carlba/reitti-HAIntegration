# Reitti Integration for Home Assistant

## Overview

The Reitti Integration allows you to push location data from Home Assistant device trackers to a Reitti server using the OwnTracks format. This integration is perfect for tracking devices and sending location updates to your own Reitti server instance.

## Features

- **Push Location Data**: Automatically sends location updates from device trackers to your Reitti server
- **Configurable Push Intervals**: Set custom intervals for location updates (5-3600 seconds)
- **State Change Triggers**: Pushes location data immediately when device state changes
- **Manual Push Service**: `reitti.push_now` service for on-demand location updates
- **Debug Logging**: Optional debug mode for troubleshooting
- **Reconfiguration Support**: Modify settings without removing and re-adding the integration

## Configuration

### Initial Setup

1. Go to **Settings** → **Devices & Services** → **Add Integration**
2. Search for "Reitti Integration"
3. Enter your configuration:
   - **Reitti Server URL**: URL of your Reitti server (e.g., `http://reitti-server`)
   - **Port**: Server port (default: 8080)
   - **API Key**: Your Reitti API token
   - **Device**: Select the device tracker to monitor
   - **Push Interval**: How often to send updates (default: 30 seconds)
   - **Enable Push**: Whether to enable automatic pushes
   - **Debug Logging**: Enable for troubleshooting
   - **Friendly Name**: Custom name for this integration instance

### Reconfiguration

You can modify the integration settings at any time:

1. Go to **Settings** → **Devices & Services**
2. Find your Reitti Integration
3. Click the **Configure** button
4. Update your settings as needed

### Options

Access additional options through the integration's options menu:

- **Push Interval**: Adjust how frequently location data is sent
- **Debug Logging**: Toggle debug mode on/off
- **Enable Push**: Enable or disable automatic location pushing
- **Friendly Name**: Change the display name

## Services

### `reitti.push_now`

Manually trigger an immediate location update to your Reitti server.

```yaml
service: reitti.push_now
```

## Requirements

- Home Assistant 2024.4.1 or newer
- A running Reitti server instance
- Valid API token for your Reitti server
- At least one device tracker entity in Home Assistant

## Supported Data

The integration sends location data in OwnTracks format including:

- Latitude and longitude coordinates
- Altitude (if available)
- GPS accuracy
- Timestamp
- Device identifier (TID)

## Troubleshooting

1. **Enable debug logging** in the integration options
2. Check the Home Assistant logs for error messages
3. Verify your Reitti server is accessible from Home Assistant
4. Confirm your API token is valid
5. Ensure the selected device tracker has location data

## Support

For issues, feature requests, or questions:

- [GitHub Issues](https://github.com/karldonteljames/reitti-HAIntegration/issues)
- [Documentation](https://github.com/karldonteljames/reitti-HAIntegration/blob/main/README.md)