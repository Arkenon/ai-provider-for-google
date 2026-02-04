=== Google AI Provider ===
Contributors: WordPress AI Team
Tags: ai, gemini, artificial-intelligence
Requires at least: 6.9
Tested up to: 6.7
Stable tag: 1.0.0
Requires PHP: 7.4
License: GPL-2.0-or-later
License URI: https://www.gnu.org/licenses/gpl-2.0.html

Google AI (Gemini) provider for the PHP AI Client SDK.

== Description ==

This plugin provides Google AI (Gemini) integration for the PHP AI Client SDK. It enables WordPress sites to use Google's Gemini models for text generation, image generation, and other AI capabilities.

**Features:**

* Text generation with Gemini models
* Image generation with Imagen models
* Function calling support
* Automatic provider registration

**Supported Models:**

Models are dynamically discovered from the API. Current flagship models include:

* gemini-3-pro, gemini-3-flash (latest)
* gemini-2.5-pro, gemini-2.5-flash, gemini-2.5-flash-lite
* imagen-3.0-generate-002 (image generation)

**Requirements:**

* PHP 7.4 or higher
* PHP AI Client plugin must be installed and activated
* Google API key

== Installation ==

1. Ensure the PHP AI Client plugin is installed and activated
2. Upload the plugin files to `/wp-content/plugins/google-ai-provider/`
3. Activate the plugin through the 'Plugins' menu in WordPress
4. Configure your Google API key via the `GOOGLE_API_KEY` environment variable or constant

== Frequently Asked Questions ==

= How do I get a Google API key? =

Visit the [Google AI Studio](https://aistudio.google.com/) to create an API key for the Gemini API.

= Does this plugin work without the PHP AI Client? =

No, this plugin requires the PHP AI Client plugin to be installed and activated. It provides the Google-specific implementation that the PHP AI Client uses.

== Changelog ==

= 1.0.0 =
* Initial release
* Support for Gemini text generation models
* Support for Imagen image generation models
* Function calling support

== Upgrade Notice ==

= 1.0.0 =
Initial release.
