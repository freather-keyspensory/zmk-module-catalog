# Keyspensory ZMK module catalog

This is the default editor catalog for the Keyspensory keyboard configurator. The app matches identifiers reported by the connected keyboard with entries in [catalog.json](catalog.json). The repository lists upstream projects and their hosted editors. Firmware modules are included when the keyboard firmware is built.

## Add an editor

Submit a pull request updating `catalog.json`. Use the exact subsystem identifier registered by the firmware and link to the upstream repository and its working HTTPS editor. Each identifier has one entry. Keep the list sorted by name.

## Publish a community repository

Put a version 1 `catalog.json` on your repository's default branch. In **Studio modules → Repositories**, paste the public GitHub repository URL or the HTTPS URL of the JSON file. One repository can provide multiple modules.

```json
{
  "version": 1,
  "name": "My keyboard editors",
  "modules": [
    {
      "id": "cormoran__os_detection",
      "name": "Host operating system",
      "repository": "https://github.com/cormoran/zmk-feature-os-detection",
      "editorUrl": "https://cormoran.github.io/zmk-feature-os-detection/"
    }
  ]
}
```

For a ZMK module with a published GitHub Pages editor, the repository URL also works without a catalog file when the firmware advertises the same editor URL. A catalog entry with the exact subsystem identifier also works with firmware that omits its editor URL. Standalone editors open in their own tab and connect directly to the keyboard.
