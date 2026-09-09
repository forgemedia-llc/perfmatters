=== Perfmatters ===
Contributors:
Donate link: https://perfmatters.io
Tags: perfmatters
Requires at least: 5.5
Requires PHP: 8.1
Tested up to: 7.1
Stable tag: 2.6.8
License: GPLv2 or later
License URI: https://www.gnu.org/licenses/gpl-2.0.html

Perfmatters is a lightweight performance plugin developed to speed up your WordPress site.

== Description ==

[Perfmatters](https://perfmatters.io/) is a lightweight web performance plugin designed to help increase Google Core Web Vitals scores and fine-tune how assets load on your site.

= Features =

* Easy quick toggle options to turn off resources that shouldn't be loading. 
* Disable scripts and plugins on a per post/page or sitewide basis with the Script Manager.
* Add and optimize code snippets (PHP, CSS, JS, and HTML), only load where needed.
* Defer and delay JavaScript, including third-party scripts.
* Automatically remove unused CSS.
* Minify JavaScript and CSS.
* Preload resources, critical images, and prerender links for quicker load times.
* Lazy load images and enable click-to-play thumbnails on videos.
* Host Google Analytics and Google Fonts locally.
* Change your WordPress login URL. 
* Disable and limit WordPress revisions.
* Add code to your header, body, and footer.
* Optimize your database.

= Documentation =

Check out our [documentation](https://perfmatters.io/docs/) for more information on how to use Perfmatters.

== Changelog ==

= 2.6.8 - 09.09.2026 =
* Added new Inline Excluded Stylesheets advanced option to automatically inline stylesheets excluded from Remove Unused CSS.
* Added new Safe Mode option to disable all Perfmatters performance optimizations sitewide without impacting security-related options or code snippets.
* Added new Load in Block Editor option for frontend CSS code snippets so those styles can also appear in the WordPress block editor canvas.
* Added new perfmatters_inline_scripts filter which allows you to inline specific local JavaScript files.
* Improved stylesheet inlining via the new perfmatters_inline_stylesheets filter (perfmatters_rucss_inline_stylesheets still supported), which can now run independently of Remove Unused CSS while still deferring to RUCSS for non-excluded stylesheets.
* Made some adjustments to code snippets UI visibility script.
* Moved Instant Page, Preconnect, and DNS Prefetch into the main Perfmatters queue so they respect the same request-level disable checks as other front-end optimizations.
* Removed redundant admin and ?perfmattersoff checks from FastClick output, which is already gated by the main Perfmatters queue.
* Fixed a PHP warning in Minify class when parse_url() returned false for a malformed script or stylesheet URL.
* Fixed a PHP fatal error that could stop buffer optimizations from running when one-per-line options were stored as a string instead of an array.
* Improved Remove Unused CSS to detect local stylesheets from the URL path, which should resolve most third-party CDN rewrites without needing the CDN URL setting or local stylesheet filter.
* Fixed an issue where Remove Unused CSS could delay, async, or remove external stylesheets that were never included in used CSS.
* Fixed get_file_path incorrectly stripping characters from asset paths on subdirectory installs in certain cases.
* Fixed a compatibility issue with Infinite Uploads that prevented code snippets from loading correctly.
* Fixed an issue where Perfmatters meta options were not available when creating a new post or page until after saving.
* Fixed an issue where code snippet filenames with non-ASCII characters (such as Korean) were incorrectly encoded on disk.
* Added missing license notices for bundled third-party libraries.

= 2.6.7 - 08.06.2026 =
* Removed the Script Manager MU Mode dependency on pluggable.php to avoid conflicts with SMTP and other plugins that override core pluggable functions.
* Fixed an issue where Script Manager MU Mode could permanently deactivate plugins when another plugin (such as Freemius) wrote a filtered active_plugins list back to the database.
* Fixed an issue where Script Manager MU Mode could resolve some custom post type URLs to the wrong post ID.
* Fixed an issue where Fetch Priority would always use the first matched priority value when the same selector had separate device rules.
* Added ABSPATH checks to plugin include files where needed.
* Added capability checks to Used CSS and Minify clear actions, and sanitized the Used CSS file type parameter.
* Hardened license form request verification.
* Improved license and update API request handling to reduce how often sites contact the Perfmatters server, including longer update check caching, cached license status checks, and a staggered retry delay after failed update requests.

= 2.6.6 - 07.09.2026 =
* Improved code snippet docblock parsing to use UTF-8 aware regex when reading snippet metadata.
* Improved reliability of snippet metadata parsing across different server environments.
* Fixed an issue with multiline code snippet descriptions not saving properly. 
* Fixed an issue where the database optimization process button spinner was getting stuck without reloading the page.
* Translation updates.

= 2.6.5 - 06.30.2026 =
* Added new perfmatters_rucss_delay_stylesheets filter which allows you to delay a specific stylesheet already excluded from used CSS.
* Added new load behavior option to delay CSS code snippets using the file print method.
* Added new code snippet URL-based conditions for path contains, path equals and path regex.
* Added additional support to code snippet search to allow the search value to match on the code input itself.
* Added default sort order controls to code snippet screen options.
* Made a change to allow an image tag with a missing src attribute to still be able to lazy load if it has a valid srcset attribute.
* Adjusted main code menu behavior to return to return to the base code view if selected while viewing a single code snippet.
* Fixed utility attribute encoding so certain characters are preserved instead of being converted to HTML entities.
* Fixed a possible JavaScript conflict with minimal analytics declaring variables in the global scope. The script is now wrapped in an IIFE for compatibility.
* Security update to improve escaping of Code Snippets list table admin links built from the current request URL.
* Security updates to add domain verification and content type validation to local Google fonts feature when downloading remote files.
* Translation updates.

= 2.6.4 - 06.01.2026 =
* Security updates to improve PMCS admin output sanitization and query handling across snippet editor and list views.
* Translation updates.

= 2.6.3 - 05.27.2026 =
* Added new Shortcode option when choosing a location for HTML code snippets.
* Added new code option to select the Editor Theme along with the ability to upload a custom CodeMirror 5 theme stylesheet.
* Added base64 encoding to exported code snippets to prevent import requests from being blocked by certain firewalls. Previously exported code snippet JSON files can still be imported.
* Added new Location helper class to store shared logic to parse and match string based location input fields throughout the plugin.
* Added the ability to use the 'front' keyword in location input fields to always match the front page of the site.
* Added additional lazy loading compatibility styles specifically for iframes placed inside Elementor text and HTML elements.
* Adjusted Script Manager Global View rows to always display multiple post IDs in ascending order.
* Multiple styling adjustments and fixes throughout the plugin UI.
* Made some changes to how certain UI elements trigger a forced reload in response to specific actions to make things less jarring.
* Fixed an issue where our compatibility styles for a lazy loaded video inside a responsive embed could break the layout if the core block library stylesheet was disabled. 
* Fixed an issue where code type selection for individual code snippets was still visible even after saving.
* Fixed an issue where the next page buttons in the snippets table was still showing as active even when viewing the last page.
* Fixed an issue where stylesheets with protocol-relative URLs were not getting parsed for used CSS.
* Disabled lint markers for HTML code snippets, as they do not currently work for combined HTML and inline PHP code.
* Removed unnecessary instances of perfmatters-lazy-youtube class from lazy loading inline styles. All lazy loading video features are now using a shared perfmatters-lazy-video class.
* Removed unnecessary development directories from plugin files.
* Translation updates.

= 2.6.2 - 04.29.2026 =
* Added support to automatically optimize and lazy load Elementor Atomic YouTube elements and legacy video widgets when Perfmatters iframe lazy loading is turned on. YouTube preview thumbnails are also supported, as well as Elementor image overlays if set for the video.
* Added request-level caching to excluded and forced lazy loading attribute arrays to prevent unnecessary calls.
* Added multiple stripos and str_contains (PHP 8) checks in lazy loading image and iframe functions to prevent expensive regex scans if tags don't exist on the page.
* Added new should_skip_request method in core LazyLoad class with request-level caching to prevent duplicate checks for WooCommerce pages and post-specific meta options.
* Added support to various General class functions to respect ?perfmattersoff.
* Added filters back to turn off WordPress' lazy loading and auto sizing styles when Perfmatters lazy loading is turned on.
* Added built-in JS and CSS exclusions for Woocommerce's dynamically added woocommerce-js body class.
* Refactored LazyLoad class into multiple subclasses for better maintainability.
* Removed duplicate list normalization step before replacement across LazyLoad classes to reduce loop overhead.
* Renamed previous Images class to ImageDimensions to make room for new Images lazy loading subclass.
* Fixed an issue where certain lazy loaded tags were getting replaced globally in the document instead of only at the specific tag match instance.
* Translation updates.

= 2.6.1 - 04.10.2026 =
* Made additional plugin UI styles adjustments in preparation for WordPress 7.
* Made some adjustments to our code snippets error handler initialization logic to avoid unnecessary handling if no relevant code snippets are active.
* Updated our exception_handler method with more specific error logging when our handler is dealing with an error outside of our code snippets.
* Updated Disable RSS Feeds tooltip text to reflect the recent header changes in the previous update.
* Fixed an error that would occur when UTF-8 stylesheets with specific multibyte characters were parsed for used CSS.
* Fixed multiple incorrect form label IDs that showed up when creating a new code snippet.
* Fixed an issue with Disable Self Pingbacks functionality that was introduced after the functions.php refactor.
* Fixed an issue where a JS or CSS file preloaded dynamically by handle would not serve the minified version of the file in certain cases.
* Fixed an issue where the inline stylesheet fallback was not always converting relative URLs correctly if certain characters were present in the string.
* Translation updates.

= 2.6.0 - 03.25.2026 =
* Increased minimum required PHP version to 8.1 to allow for library updates and support for future codebase performance improvements.
* Added new perfmatters_rucss_logged_in filter.
* Added PHP Scoper to our plugin development workflow to be able to silo specific third-party libraries to prevent conflicts with other plugins.
* Updated PHP CSS Parser library to 9.3.0.
* Added additional logic to used CSS generation to better deal with layer elements that are declared without a content block.
* Removed built-in stylesheet exclusion for Bricks' layer files. We recommend clearing used CSS after updating.
* Added new CSS helper method to rewrite relative URLs in stylesheets that will be printed inline using regex only to prevent having to pass them through the parser.
* Updated code snippets author column to use the user's display name instead of nice name to match the single snippet layout.
* Updated disable RSS feeds function to return a 410 header instead of a 301 when requesting a feed URL.
* Made some adjustments to clean_html regex pattern to avoid potential backtracking which could end up hitting a PCRE limit in some cases.
* Made plugin UI styles adjustments in preparation for WordPress 7.
* Made improvements to visual transitions during hard reloads in the plugin UI.
* Made some changes to plugin UI nav JS to improve compatibility when wrapper elements are added in the HTML from another source.
* Fixed an issue that was causing certain attribute values to conflict with the HTML parent selector matching regex.
* Fixed an issue where specific WooCommerce product types were not getting the built-in product exclusion selector added to generated used CSS.
* Fixed an issue where HTML snippets with a condition mismatch were causing the original content to return blank.
* Fixed an issue where code snippet input preserved in the form after a failed save request was not properly unslashed.
* Fixed an issue where the code snippet code type was no longer visible and the selected value was lost after a failed save request.
* Fixed a possible PHP 8.2+ deprecation warning that could occur in specific server environments during PMCS initialization.
* Code snippet security updates to form submission handling.

= 2.5.9 - 02.27.2026 =
* Fixed a type cast issue in wp_headers filter that was resulting in a PHP error in cases where the headers were already being filtered and returning null.

= 2.5.8 - 02.26.2026 =
* Added new perfmatters_lazyload_data_src filter.
* Added nav selector support for functions that target elements inside parent containers.
* Added additional built-in CSS selector exclusion for Kadence active state class.
* Added is_admin check to disable dashicons function for certain edge cases in the admin UI.
* Added logic to prevent certain redundant options from showing up in the UI when parent disables are already toggled on.
* Added new General, License and Analytics classes to separate out specific functionality.
* Fixed an issue with certain attribute pair formats not being recognized when converting an element's attribute string to an array.
* Fixed an issue where delaying certain duplicate scripts would cause a JavaScript error and prevent remaining delayed assets from loading in.
* Fixed a code snippet issue where targeting the front or blog page of the site by page ID would not match correctly.
* Fixed multiple plugin UI HTML warnings for incorrect label target IDs.
* Made some lazy loading adjustments to let WordPress still add the auto size attribute value when necessary before the Perfmatters output buffer runs.
* Made changes to the way we handle images excluded from lazy loading to ensure they don't have a loading attribute applied.
* Removed previous functions.php file, refactored and migrated the contents to new and existing classes.
* Refactored Utilities class, added a few functions from previous combined file, combined regex passes for clean_html, added memoization to necessary functions to prevent multiple runs.
* Minor update to disable self pingbacks function for better compatibility.
* Removed BETA tag from Code Snippets feature.
* Translation updates.

= 2.5.7 - 02.02.2026 =
* Fixed an issue where the auto size attribute value was being added to images with no specified dimensions which could cause the image to display incorrectly.
* Fixed an issue where the attribute parser would ignore attribute values containing new line characters.
* Fixed an issue with certain attribute characters being disallowed preventing the attribute from migrating to the final element tag.

= 2.5.6 - 01.28.2026 =
* Added new perfmatters_cdn_url filter along with new helper methods in the CDN class.
* Added the ability to completely disable Perfmatters code features using the new PERFMATTERS_DISABLE_CODE constant.
* Added confirmation message when turning on FastClick option.
* Added logic to remove the previous stored author ID when a code snippet is imported.
* Added host name to global settings and code snippet export files.
* Added additional logic to add an auto value to lazy loaded images sizes attributes when needed.
* Added separate used CSS generated files for different WooCommerce product types.
* Added dynamic request check in heartbeat function to prevent a possible PHP error.
* Updated lazy loading class to no longer add noscript tags by default for images and iframes to reduce HTML page size. The perfmatters_lazyload_noscript filter can still be used to turn that behavior back on.
* Updated get_atts_array utility method to use regex instead of wp_kses_hair for better compatibility.
* Reworked code snippet error handling class to work better with other exception handlers and existing error reporting.
* Turned off CSSLint in the code snippet editor, as it is outdated and was leading to false positives.
* Adjusted gutter column layout in the code snippet editor to be more consistent between different code types.
* Adjusted code snippet priority field to allow both negative and zero input values.
* Fixed an issue where CSS code snippets set to run in the footer were not having their conditions checked.
* Fixed an issue where CSS code snippets were not always printing where expected based on the set location and priority.
* Fixed an issue with certain code snippet input fields not being escaped properly in the UI leading to a broken layout in some cases.
* Fixed an issue where YouTube iframes rendered with a preview thumbnail that had autoplay forced off in their query string would require a double click.
* Fixed an issue where the referrerpolicy iframe attribute did not get applied to the generated iframe when using YouTube preview thumbnails.
* Translation updates.

= 2.5.5 - 12.11.2025 =
* Added new Code Settings options to Import and Export Perfmatters code snippets.
* Added support to export individual snippets, a subset of snippets through a bulk action, or all stored snippets from the new Code Settings export button.
* Added code snippets admin bar menu item that will show up if at least one snippet is present.
* Added frontend footer and admin footer locations for CSS code snippets.
* Added new PMMU_PLUGIN_DIR constant to allow for manipulation of the MU plugin file location for specific setups where the standard WPMU_PLUGIN_DIR may be altered.
* Added a REST API exception for Mollie.
* Added additional built-in CSS selector exclusions for Elementor's background slideshow.
* Added support for relative path URLs found inside stylesheets printed inline with our perfmatters_rucss_inline_stylesheets filter.
* Updated previous Separate Block Styles option which will now show up as a Block Style Behavior dropdown for sites running WordPress 6.9+.
* Fixed an issue in the code snippets editor where lint markers were not always correctly displaying for HTML and CSS snippets.
* Fixed an issue where the code snippet editor was pushing new lines off screen in some cases and not automatically scrolling to keep things in view.
* Fixed an issue where HTML code snippets were not able to save a non-default location.
* Fixed an issue with general Perfmatters admin notices not displaying correctly.
* Fixed multiple duplicate ID warnings in the plugin UI.
* Fixed multiple jQuery deprecation warnings in plugin UI JavaScript.
* Translation updates.

= 2.5.4 - 11.20.2025 =
* Moved code snippet storage location out of cache directory and into the uploads folder to prevent data loss in certain environments.
* Fixed a code snippets compatibility issue with servers that don't support PHP OPcache.
* Fixed an issue where the CodeMirror editor was not always initializing correctly when editing an individual code snippet.
* Fixed an issue where the code type tag prefix was not updating when changing the code type while creating a new code snippet.
* Fixed an issue in the error handling class where the exception handler was looping in certain instances and throwing an error.

= 2.5.3 - 11.19.2025 =
* Added new Code Snippets (BETA) feature, which is now the default view in the Code tab. You can now create and manage PHP, JS, CSS, and HTML code snippets from inside Perfmatters. We store and load code snippets using a flat-file method and directly integrate with all of our existing optimization options for the best performance.
* Moved the existing header, body, and footer code boxes to Code > Global Scripts.
* Made style adjustments throughout the plugin UI.
* Added built-in CSS selector exclusion for GeneratePress mobile menu.
* Added new get_file_path utility method for use in various functions that need to determine the local file path for an asset loading on the front end.
* Fixed an issue where missing image dimensions were not getting applied correctly for sites inside a subdirectory.
* Removed BETA tag from Cloudflare Early Hints option.
* Updated EDD plugin updater class to version 1.9.4.

= 2.5.2 - 10.23.2025 =
* Added new perfmatters_rucss_inline_stylesheets filter which allows you to inline any stylesheet already excluded from used CSS.
* Reworked the Script Manager input change event listener for better compatibility with other JavaScript running while the Script Manager is being used.
* Added new delay JS quick exclusion for GenerateBlocks Pro.
* Added built-in CSS selector exclusion for GenerateBlocks mobile menu.
* Added built-in stylesheet exclusion for GeneratePress local fonts.
* Updated WS Form Pro delay JS quick exclusion to fix a console error.
* Fixed some incorrect wording in the clear used CSS tooltip.

= 2.5.1 - 09.29.2025 =
* Added a fetchpriority high attribute on critically preloaded image tags to match the preload link attribute.
* Added new buffer function to check the viewport meta tag position and adjust it if needed when critical image preloads are being used.
* Added logic to populate critical image preload href attribute with the fallback image src if the preload is for a responsive image srcset.
* Added built-in stylesheet exclusion for GeneratePress offside menu.
* Updated delay JS quick exclusion for Elementor to include e-gallery.
* Fixed a PHP warning that could sometimes happen when calculating the root directory path in the Utilities class.
* Fixed a trailing slash validation warning coming from critical image preload tags.
* Disabled Remove Comment URLs toggle when Kadence is active due to an incompatibility.
* Translation updates.

= 2.5.0 - 08.26.2025 =
* Added new WP-CLI subcommands to clear-minified-js, clear-minified-css, and clear-local-fonts.
* Added support for targeting header element when using parent selector matching functions.
* Added support to enable and disable the clean uninstall option in WP-CLI.
* Added a built-in Script Manager rule to prevent dashicons from being dequeued when logged in.
* Fixed a WP-CLI issue where license activation and deactivation subcommands were not working correctly. 
* Translation updates.

= 2.4.9 - 08.12.2025 =
* Rolled back CSS parsing library one version (8.9.0) to fix a conflict with WooCommerce.

= 2.4.8 - 08.11.2025 =
* Added built-in stylesheet exclusion for Bricks layer stylesheets.
* Adjusted emoji_svg_url filter to only return false outside the admin dashboard.
* Updated delay JS quick exclusion for Bricks to include splide.
* Updated delay JS quick exclusion for CookieYes to be more compatible.
* Updated early hint attribute check to include sizes and media attributes.
* Updated CSS parsing library to the latest version (9.0.0). New features, deprecation removals and bug fixes.
* Updated deprecated function in CSS class to use current method.
* Updated minification library to the latest version (1.3.75).
* Updated minimum PHP version requirement to 7.2.
* Updated our staging site license key exception list with additional formats.
* Translation updates.

= 2.4.7 - 07.15.2025 =
* Added support to set the Perfmatters license key via wp-config.php using the PERFMATTERS_LICENSE_KEY constant.
* Added new perfmatters_fetch_priority filter.
* Added integration to send an early hint header for used CSS file when both features are enabled.
* Added additional check for imagesrcset attribute when determining if an image should receive an early hint.
* Added crossorigin and fetchpriority attributes to early hint headers.
* Added additional parameters to excluded page builders array for Thrive Quiz Builder and Etch.
* Added built-in stylesheet exclusions for Elementor and Astra local fonts.
* Cleaned up leftover test file missed in previous update.
* Translation updates.

= 2.4.6 - 06.17.2025 =
* Added new advanced preload option to enable Cloudflare Early Hints (BETA) for Perfmatters preloads along with controls to limit which file types will have early hint link headers sent.
* Added new WP-CLI import-settings subcommand to import a settings configuration from an exported .json file.
* Added new WP-CLI disable and enable subcommands to modify certain plugin options. Available options can be printed out with the new get-options subcommand.
* Added new delay JS quick exclusion for SureCart.
* Added additional logic to disable speculative loading on WooCommerce cart and checkout URLs.
* Added additional logic to allow fallback deferral exclusions as part of an existing delay JS quick exclusion.
* Added built-in exclusion for Gravity Forms to prevent optimization features from running on AJAX form requests.
* Updated CSS parsing library to the latest version (8.8.0). Bug fixes and deprecations.
* Adjusted placement of perfmatters_preloads filter which was running too early and causing some filter snippets to be ignored.
* Increased default delay timeout from 10 to 15 seconds to improve compatibility.
* Fixed an issue with certain parent selector matching functions where a child element selector tag would also be replaced if it had the exact same selector tag HTML as the matched parent tag.
* Fixed multiple redundant calls to retrieve Script Manager settings row when loading the Script Manager UI.

= 2.4.5 - 05.16.2025 =
* Added some compatibility logic to fix an issue with specific caching plugins that were not working correctly with Perfmatters output buffer functions.
* Fixed a PHP translation warning that was coming from some post meta UI functions running too early.
* Translation updates.

= 2.4.4 - 05.08.2025 =
* Added new Exclude Leading option for CSS background images.
* Added new perfmatters_lazyload_parent_exclusions filter.
* Added new perfmatters_css_background_selectors filter.
* Added new speculative loading mode option to disable the feature entirely.
* Refactored lazy element method to be more efficient when searching for multiple element selectors.
* Reworked the perfmatters_critical_image_parent_exclusions and perfmatters_leading_image_parent_exclusions filters to no longer need to process the page HTML through DOMDocument for better stability, faster parsing, and 30% less code.
* Fixed an issue with parent selector matching for fetch priority and lazy loading where only the first image tag would match if it was inside a nested container element.
* Fixed an issue where the CSS Background class would get added to child elements as well if they also contained a matching selector.
* Fixed a compatibility issue when using Perfmatters preloads alongside WP Rocket.
* Fixed a spacing issue with input row checkboxes in the plugin UI.
* Translation updates.

= 2.4.3 - 04.15.2025 =
* Added new preload options to control Speculative Loading mode and eagerness settings for sites running WordPress 6.8+.
* Deprecated Instant Page option throughout the plugin for sites running WordPress 6.8+.
* Added a REST API exception for Slider Revolution.
* Updated delay JS quick exclusions for ShortPixel Adaptive Images and Slider Revolution to be more compatible.

= 2.4.2 - 04.02.2025 =
* Fixed an issue where mobile event handlers were sometimes preventing the delayed click from firing.
* Translation updates.

= 2.4.1 - 03.26.2025 =
* Refactored delay JS inline script, removed pageshow event listener, and uglified final code, reducing the script size by over 15%.
* Added built-in JS deferral exclusion for Cloudflare Turnstile.
* Added new delay JS quick exclusion for Plausible Analytics.
* Updated delay JS quick exclusions for Fluent Forms and Kadence Blocks to be more compatible.
* Adjusted document.write built-in delay exclusion to prevent false positives.
* Adjusted MU Mode documentation links in the Script Manager to go to specific anchor link sections.
* Fixed an issue where encoded data attribute values weren't being preserved correctly when converting an elements attribute string to an array.
* Fixed a multisite issue where the root directory path was not determined correctly when using a custom content directory setup.
* Deployed a secondary API that can be used when the client has issues communicating with our licensing server (usually due to firewalls).
* Removed deprecated SVG duotone filter removal actions from global styles toggle and updated tooltip to reflect changes.
* Translation updates.

= 2.4.0 - 02.26.2025 =
* Added new perfmatters_rucss_async_stylesheets filter which allows you to async any stylesheet already excluded from used CSS.
* Dashicons and Elementor animation stylesheets are now loaded via async for better performance when Removed Unused CSS is turned on.
* Added additional logic to better handle stylesheets with media query attributes when including them in used CSS for increased performance. WooCommerce users may need to clear their used CSS if mobile-specific stylesheets are being loaded as they have been removed from our built-in exclusions.
* Added new built-in stylesheet exclusion for Bricks post-specific CSS.
* Added new Delay JS quick exclusion for WPBakery.
* Added a REST API exception for SureCart.
* Added additional compatibility styles to the Script Manager.
* Made some changes to be able to start our main output buffer a bit earlier in the load for better compatibility with other plugins that modify the HTML document.
* Updated clean uninstall function with current post meta options.
* Fixed an issue where the Clear Used CSS meta button was not working correctly for certain URL types.
* Fixed a PHP warning coming from certain rewrite rule formats when MU Mode was turned on.
* Removed BETA tag from preload lazy elements option.
* Updated our staging site license key exception list with additional formats.

= 2.3.9 - 02.06.2025 =
* Added new perfmatters_preloads_array filter.
* Added new perfmatters_minify_threshold filter.
* Added additional swiper JavaScript file to Elementor quick exclusion.
* Added additional built-in CSS selector exclusion for WP Armour.
* Added a string check to login URL filter function to prevent a possible PHP error.
* Fixed an issue where new user email requests were not being allowed through the redirect block when using a custom login URL.
* Minor adjustment to CDN rewrite regex to fix an issue that was happening when the home URL was different from the site URL.
* Removed Ezoic quick exclusion and moved to built-in deferral and delay exclusions.
* Updated our staging site license key exception list with additional formats.
* Translation updates.

= 2.3.8 - 01.07.2025 =
* Added a REST API exception for SureForms.
* Added a UI button to cancel the current database optimization process.
* Added built-in delay JS exclusion for document.write for compatibility.
* Updated background processing library to the latest version (1.4.0).
* Fixed an issue where some deliberate redirect requests were not being allowed to access the hidden login URL.
* Fixed an issue where the database optimization process was not starting correctly in some cases.
* Fixed a missing anchor link pointing to the license tab in our plugin settings UI.

= 2.3.7 - 01.01.2025 =
* Added additional CSS background image inline styles to account for backgrounds set on pseudo-elements of children inside the targeted container.
* Added WP Rocket filter to disable their critical image optimization when preload critical images is active to prevent conflicts.
* Added new Delay JS quick exclusion for Ezoic.
* Added built-in minify JS exclusion for WP Recipe Maker.
* Updated network default function to preserve the CDN URL if already set on the target subsite.
* Updated admin bar menu items to show clear all used CSS on the front end.
* Updated minify exclusion functions to check the entire attribute string of the script or stylesheet instead of just the source URL.
* Updated CSS parsing library to the latest version (8.7.0). Improves support for PHP 8.4.
* Updated login URL feature with additional check to prevent access to the hidden login slug via an authentication request redirected from a query string.
* Updated buffer class to prevent running on Bricks template URLs.
* Fixed an issue where the Used CSS file was sometimes getting falsely flagged as completely unused on certain speed tests.
* Removed unnecessary documentWrite handling function from delay JS inline script to reduce the size by over 8%.
* Removed older changelog entries in readme.txt file and added link to web version.

View the full changelog:
[https://perfmatters.io/docs/changelog/](https://perfmatters.io/docs/changelog/)
