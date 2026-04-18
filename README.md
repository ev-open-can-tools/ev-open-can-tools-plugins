# EV Open CAN Tools Plugins

This repository contains ready-to-use example plugins for the EV Open CAN Tools plugin system.

Plugins are distributed as JSON files and can be installed through the EV Open CAN Tools dashboard without rebuilding firmware. This repository serves as a central place to host reusable plugin examples for supported hardware variants.

## What is in this repository

The repository is organized by hardware platform:

- `HW3/` for HW3-compatible plugin examples
- `HW4/` for HW4-compatible plugin examples

Each file is a standalone plugin in JSON format.

## Available plugin examples

### HW3

- `ad-activation-hw3.json`
- `bypass-tlssc-hw3.json`
- `summon-eu-unlock-hw3.json`

### HW4

- `ad-activation-hw4.json`
- `bypass-tlssc-hw4.json`
- `emergency-vehicle-detection-hw4.json`
- `hw4-speed-offset-plus-5.json`
- `hw4-speed-offset-plus-7.json`
- `hw4-speed-offset-plus-10.json`
- `hw4-speed-offset-plus-15.json`
- `isa-chime-suppress-hw4.json`
- `summon-eu-unlock-hw4.json`

## How to use these plugins

You can install plugins from the EV Open CAN Tools dashboard in one of these ways:

1. Open the dashboard on your device
2. Go to the Plugins section
3. Install a plugin by:
   - pasting a direct raw GitHub URL
   - uploading the JSON file
   - pasting the JSON content directly

### Example raw GitHub URL

`https://raw.githubusercontent.com/ev-open-can-tools/ev-open-can-tools-plugins/main/HW4/ad-activation-hw4.json`

## Choosing the right plugin

Always use the plugin that matches your hardware platform.

- Use files from `HW3/` for HW3 targets
- Use files from `HW4/` for HW4 targets

Do not assume that a plugin for one hardware version is safe or correct for another.

## Plugin format

Each plugin is a JSON file that follows the EV Open CAN Tools plugin schema.

Typical top-level fields include:

- `name`
- `version`
- `author`
- `rules`

A plugin contains one or more CAN rules. Each rule matches a CAN frame ID, applies one or more operations, and can optionally send the modified frame back on the bus.

For the full format, supported operations, limits, and dashboard workflow, see the main plugin system documentation in the EV Open CAN Tools repository.

## Repository goal

This repository exists to:

- provide reusable example plugins
- keep plugin examples separate from the main firmware repository
- make it easy to install plugins directly from hosted JSON files
- help users share and maintain community-tested rule sets

## Contributing

Contributions are welcome.

Please keep contributions consistent with the existing layout:

- place plugins in the correct hardware folder
- use clear and descriptive file names
- keep one plugin per JSON file
- include a readable plugin name, version, and author
- make sure the JSON is valid before submitting
- describe clearly what the plugin changes

It is also helpful to include:

- the intended hardware target
- a short explanation of the expected behavior
- any limitations, side effects, or known risks

## Safety notice

These plugins modify CAN-related behavior. Review every plugin before using it.

Use them at your own risk and test carefully in a safe environment. Do not rely on any example here without understanding what it does and whether it is appropriate for your vehicle, hardware, and firmware setup.

## Related repositories

- Main project: `ev-open-can-tools/ev-open-can-tools`
- Plugin repository: `ev-open-can-tools/ev-open-can-tools-plugins`

## License

This repository is licensed under GPL-3.0.