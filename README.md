# Send Telegram Message GitHub Action

This [GitHub Action](https://github.com/marketplace/actions/fast-telegram-action) allows you to send a message to Telegram using a Bash script. It can be useful for sending notifications or alerts from your workflows.

## Inputs

- `token` (required): The Telegram Bot API token.
- `to` (required): The Telegram chat ID or group ID.
- `message` (required): The message text to be sent (supports Markdown). The default value is "Hello from GitHub Actions!".
- `format` (optional): markdown or html. default is markdown.
- `disable_web_page_preview` (optional): disables notifications for this message, supports sending a message without notification. default is false.
- `photo` - (optional). photo message
- `document` - (optional): document message
- `sticker` - (optional): sticker message
- `audio` - (optional): audio message
- `voice` - (optional): voice message
- `location` - (optional): location message
- `venue` - (optional): venue message
- `video` - (optional): video message

## Example Usage

```yaml
name: Send Telegram Message

on:
  push:
    branches:
      - main

jobs:
  send-message:
    runs-on: ubuntu-latest
    steps:
      - name: Send Telegram Message
        uses: s00d/fast-telegram-action@v3
        with:
          token: ${{ secrets.TELEGRAM_TOKEN }}
          to: ${{ secrets.TELEGRAM_TO }}
          message: 'This is a test message from GitHub Actions!'
```

Make sure you have set up the `TELEGRAM_TOKEN` and `TELEGRAM_TO` secrets in your repository's settings.

## Contributing

Contributions are welcome! If you have any suggestions, bug reports, or feature requests, please create an issue or submit a pull request.

## License

This GitHub Action is licensed under the [MIT License](LICENSE).
