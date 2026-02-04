# Google AI Provider

A Google AI (Gemini) provider for the [PHP AI Client](https://github.com/WordPress/php-ai-client) SDK. Works as both a Composer package and a WordPress plugin.

## Requirements

- PHP 7.4 or higher
- [wordpress/php-ai-client](https://github.com/WordPress/php-ai-client) must be installed

## Installation

### As a Composer Package

```bash
composer require wordpress/google-ai-provider
```

### As a WordPress Plugin

1. Download the plugin files
2. Upload to `/wp-content/plugins/google-ai-provider/`
3. Ensure the PHP AI Client plugin is installed and activated
4. Activate the plugin through the WordPress admin

## Usage

### With WordPress

The provider automatically registers itself with the PHP AI Client on the `init` hook. Simply ensure both plugins are active and configure your API key:

```php
// Set your Google API key (or use the GOOGLE_API_KEY environment variable)
putenv('GOOGLE_API_KEY=your-api-key');

// Use the provider
$result = AiClient::prompt('Hello, world!')
    ->usingProvider('google')
    ->generateTextResult();
```

### As a Standalone Package

```php
use WordPress\AiClient\AiClient;
use WordPress\GoogleAiProvider\Provider\GoogleProvider;

// Register the provider
$registry = AiClient::defaultRegistry();
$registry->registerProvider(GoogleProvider::class);

// Set your API key
putenv('GOOGLE_API_KEY=your-api-key');

// Generate text
$result = AiClient::prompt('Explain quantum computing')
    ->usingProvider('google')
    ->generateTextResult();

echo $result->toText();
```

## Supported Models

This provider dynamically discovers available models from the Google AI API. Current flagship models include:

**Text Generation (Gemini 3 Series)**
- `gemini-3-pro` - Latest reasoning model for complex agentic workflows
- `gemini-3-flash` - Best for complex multimodal understanding

**Text Generation (Gemini 2.5 Series)**
- `gemini-2.5-pro` - High-capability model with adaptive thinking
- `gemini-2.5-flash` - Fast and capable with controllable thinking
- `gemini-2.5-flash-lite` - Optimized for speed and cost-efficiency

**Image Generation**
- `gemini-2.5-flash-preview-image` - Multimodal image generation
- `imagen-3.0-generate-002` - Dedicated image generation

## Configuration

The provider uses the `GOOGLE_API_KEY` environment variable for authentication. You can set this in your environment or via PHP:

```php
putenv('GOOGLE_API_KEY=your-api-key');
```

## License

GPL-2.0-or-later
