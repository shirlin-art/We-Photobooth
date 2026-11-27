# We-Photobooth Theme Library

Theme files are public, static configuration data. Do not put names, email addresses, phone numbers, payment details, private album links, or photographs in a theme file.

## File naming

Use a lowercase, URL-safe theme ID and save it as `themes/<theme-id>.json`.
The ID is used by the photobooth URL, for example:

`https://<your-site>/index.html?theme=demo-wedding`

## Version 1 configuration

```json
{
  "schemaVersion": 1,
  "id": "demo-wedding",
  "name": "Demo Wedding",
  "category": "wedding",
  "frame": {
    "bg": "#fbf6ef",
    "ink": "#6b4f45",
    "accent": "#b8935a",
    "slot": "#ffffff",
    "deco": "double",
    "nameFont": '600 {s}px "Playfair Display", serif',
    "nameSize": 120,
    "upper": false,
    "r": 0
  }
}
```

## Supported frame properties

- `bg`: a six-digit hex colour, or a two-colour array for a vertical gradient.
- `ink`, `accent`, `slot`: six-digit hex colours.
- `deco`: an existing decoration style supported by the photobooth renderer.
- `nameFont`: canvas font template. Keep the `{s}` placeholder so text can shrink to fit.
- `nameSize`: starting font size in pixels.
- `upper`: whether the event name is uppercased.
- `r`: photo-corner radius in pixels.

Only add decoration values that the current renderer already supports. New decoration artwork requires a separate renderer change.

## Workflow

1. Create a new JSON file using a unique ID.
2. Validate the JSON and check all colour values.
3. Commit it to the same branch as the Theme Library code.
4. Test it on the development deployment before publishing.
5. Generate a QR code only after the theme file is deployed and reachable.

The initial demo file is a configuration example, not a live customer theme.
