# Troubleshooting

## Request Failed

- Check internet connection
- Verify API key is correct
- Try different AI provider

## API Key Invalid

- Copy entire key without spaces
- Check key hasn't expired
- For Grok: use key from console.x.ai, not x.com

## Ollama Not Working

1. Make sure Ollama is installed and running
2. Pull a model: `ollama pull llama3.2`
3. Check models: `ollama list`
4. Confirm service running: `ollama serve`

## Common Issues

### Plugin Not Showing in Toolbar

1. Restart calibre after installation
2. Check Preferences -> Toolbars & menus
3. Make sure the plugin is enabled

### Slow Responses

- Try a different AI provider
- Check your internet connection
- Consider using a smaller/faster model

### Model List Not Loading

- Verify your API key is correct
- Check the Base URL is correct
- Try clicking "Load Model List" again
