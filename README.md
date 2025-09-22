# Consently - Cookie Consent Banner

A lightweight, customizable WordPress plugin that displays a cookie consent banner with GDPR/CCPA compliance features. No third-party APIs required.

## Features

### Core Features

- **Cookie Consent Banner/Bar**: Display at top, bottom, or as a small popup
- **Fully Customizable**: Message text, button text, colors, fonts, and positioning
- **Accept/Reject Buttons**: Mandatory accept button with optional reject button
- **Learn More Link**: Optional link to privacy policy page
- **Cookie Settings Modal**: Simple modal with toggles for different cookie categories

### Cookie Categories

- **Necessary Cookies**: Always required for website functionality
- **Analytics Cookies**: Optional cookies for website analytics
- **Marketing Cookies**: Optional cookies for advertising and marketing

### Compliance Features

- **GDPR Compliant**: Provides clear information and user choice
- **CCPA Compliant**: Allows users to opt-out of data sales
- **Consent Management**: Remembers user preferences with configurable expiry
- **No Third-Party Dependencies**: Fully self-contained

### Customization Options

- **Positioning**: Top, bottom, or popup display
- **Styling**: Custom colors, fonts, border radius, and z-index
- **Content**: Fully editable message text and button labels
- **Behavior**: Configurable cookie expiry and consent requirements

## Installation

1. Upload the `consently` folder to `/wp-content/plugins/` directory
2. Activate the plugin through the 'Plugins' menu in WordPress
3. Go to Settings > Cookie Consent to configure the plugin

## Configuration

### General Settings

- Enable/disable the cookie consent banner
- Choose banner position (top, bottom, popup)
- Customize message text and button labels
- Set cookie expiry period

### Appearance Settings

- Customize colors (background, text, buttons, borders)
- Adjust font size and border radius
- Set z-index for proper layering

### Cookie Categories

- Enable/disable different cookie categories
- Customize descriptions for each category
- Set default consent states

### Compliance

- Link to privacy policy
- Configure learn more URL
- Review compliance guidelines

## Usage

### For Website Owners

1. Configure the plugin settings in WordPress admin
2. Customize the appearance to match your website design
3. Update your privacy policy to include cookie information
4. Test the banner on your website

### For Developers

The plugin provides a JavaScript API for other scripts to check consent status:

```javascript
// Check if user has consented to analytics
if (window.Consently.hasConsent("analytics")) {
  // Load analytics scripts
}

// Get full consent object
var consent = window.Consently.getConsent();
console.log(consent);

// Listen for consent changes
window.Consently.onConsent(function (consent) {
  console.log("Consent updated:", consent);
});
```

### Script Loading Example

```javascript
// Example: Load Google Analytics only with consent
if (window.Consently.hasConsent("analytics")) {
  // Load Google Analytics
  (function (i, s, o, g, r, a, m) {
    i["GoogleAnalyticsObject"] = r;
    (i[r] =
      i[r] ||
      function () {
        (i[r].q = i[r].q || []).push(arguments);
      }),
      (i[r].l = 1 * new Date());
    (a = s.createElement(o)), (m = s.getElementsByTagName(o)[0]);
    a.async = 1;
    a.src = g;
    m.parentNode.insertBefore(a, m);
  })(
    window,
    document,
    "script",
    "https://www.google-analytics.com/analytics.js",
    "ga"
  );
}
```

## Customization

### CSS Customization

You can override the default styles by adding custom CSS:

```css
/* Custom banner styling */
.consently-banner {
  /* Your custom styles */
}

/* Custom button styling */
.consently-button {
  /* Your custom button styles */
}
```

### Hooks and Filters

The plugin provides several WordPress hooks for customization:

```php
// Modify banner content
add_filter('consently_banner_message', function($message) {
    return 'Your custom message: ' . $message;
});

// Modify consent data before saving
add_filter('consently_consent_data', function($consent) {
    // Modify consent data
    return $consent;
});
```

## Browser Support

- Chrome 60+
- Firefox 55+
- Safari 12+
- Edge 79+
- Internet Explorer 11 (with polyfills)

## Privacy and Security

- No data is sent to external servers
- All consent data is stored locally in cookies
- No tracking or analytics of user behavior
- GDPR and CCPA compliant by design

## Troubleshooting

### Banner Not Showing

1. Check if the plugin is enabled in Settings > Cookie Consent
2. Clear browser cache and cookies
3. Check for JavaScript errors in browser console
4. Verify that no other plugins are conflicting

### Styling Issues

1. Check if your theme CSS is overriding plugin styles
2. Increase z-index value in plugin settings
3. Clear any caching plugins
4. Check for CSS conflicts in browser developer tools

### JavaScript Errors

1. Check browser console for error messages
2. Ensure jQuery is loaded on your site
3. Verify that no other scripts are conflicting
4. Test with default WordPress theme

## Support

For support and feature requests, please visit the plugin's support forum or create an issue on GitHub.

## Changelog

### Version 1.0.0

- Initial release
- Cookie consent banner with multiple display options
- Cookie settings modal with category toggles
- GDPR/CCPA compliance features
- Fully customizable appearance
- Admin settings page
- JavaScript API for developers

## License

This plugin is licensed under the GPL v2 or later.

## Credits

Developed with ❤️ by Team Webvation for the WordPress community.
