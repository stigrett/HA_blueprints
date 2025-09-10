# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This repository contains Home Assistant blueprints for Frigate Camera Notifications. The blueprints send notifications to devices when Frigate events are triggered, with extensive customization options for filtering, actions, and notification appearance.

## Key Files

- **Beta.yaml** - Development version of the blueprint with latest features
- **Stable.yaml** - Stable release version for general use
- **README.md** - Main documentation with feature list and requirements
- **Guide - Configuration Options.md** - Detailed configuration documentation
- **Guide - Debug Option.md** - Debug and troubleshooting documentation

## Blueprint Structure

The YAML blueprints follow Home Assistant's automation blueprint format:
- `blueprint:` section contains metadata (name, author, requirements, description)
- `input:` section defines all configurable parameters with descriptions and selectors
- `trigger:` section handles MQTT messages from Frigate
- `action:` section contains the notification logic with extensive templating

## Software Requirements

- Minimum Home Assistant: 2024.11
- Minimum Frigate: 0.14
- Minimum Frigate Integration: 5.7.0 (with unauthenticated proxy enabled)
- MQTT broker connected to HA and Frigate
- iOS minimum version: 15.0

## Common Development Tasks

When modifying the blueprints:

1. **Testing changes**: Test in Beta.yaml first before promoting to Stable.yaml
2. **Version updates**: Update version number in blueprint name (e.g., "0.14.0.3h")
3. **Documentation**: Update README.md for feature changes and Guide files for configuration changes

## Key Features to Consider

The blueprint supports:
- Multiple camera selection
- Mobile devices, Android/Fire TV, and notification groups
- Extensive filtering (zones, objects, presence, state, time)
- Custom notification appearance (title, message, color, icon, sounds)
- Action buttons and tap actions
- Telegram integration
- Debug mode for troubleshooting
- Multiple Frigate instances via Client ID