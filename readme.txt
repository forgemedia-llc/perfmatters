=== Perfmatters ===
Contributors:
Donate link: https://perfmatters.io
Tags: perfmatters
Requires at least: 5.5
Requires PHP: 7.2
Tested up to: 6.8.2
Stable tag: 2.5.1
License: GPLv2 or later
License URI: https://www.gnu.org/licenses/gpl-2.0.html

Perfmatters is a lightweight performance plugin developed to speed up your WordPress site.

== Description ==

[Perfmatters](https://perfmatters.io/) is a lightweight web performance plugin designed to help increase Google Core Web Vitals scores and fine-tune how assets load on your site.

= Features =

* Easy quick toggle options to turn off resources that shouldn't be loading. 
* Disable scripts and plugins on a per post/page or sitewide basis with the Script Manager. 
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

= 2.3.6 - 11.21.2024 =
* Fixed an issue where Delay JS wasn't running correctly in some cases.

= 2.3.5 - 11.21.2024 =
* Added new local Google Font option to Limit Subsets that are downloaded and included in the stylesheet.
* Added new local Google font option to change the Print Method with options for file and inline.
* Added new Priority option to manual preloads which can be used to add a specific fetchpriority attribute value to individual preload tags.
* Added new perfmatters_lazy_element_selectors filter.
* Removed unnecessary trailing link tag from delayed stylesheets when using Remove Unused CSS.
* Removed crossorigin option for manual preloads. The attribute is now automatically added to fetch and font preload tags.
* Increased action button response message timeout to 10 seconds in plugin UI.
* Fixed a PHP warning coming from Disable Google Maps function if a post ID was not found on a single post URL.
* Fixed an issue with WordPress 6.7.1 where the text domain for translations was loading too early.
* Removed deprecated plugin option to load Google fonts asynchronously.
* Translation updates.

= 2.3.4 - 10.10.2024 =
* Added new perfmatters_lazy_elements filter.
* Added new perfmatters_is_woocommerce filter.
* Added additional built-in stylesheet and selector exclusions for better compatibility with Elementor animations.
* Added WP Rocket filter to disable lazy render when lazy elements feature is active to prevent conflicts.
* Added additional parameter to excluded page builders array for tagDiv Composer.
* Added built-in delay JS exclusion for lazy elements inline script.
* Moved plugin settings logo SVG back to inline to prevent file_get_contents errors in certain environments.
* Adjusted built-in CSS dynamic selector exclusions to fix some minor visual issues with a few page builders.
* Fixed a JavaScript error that would sometimes show up in the console when using Delay JS with click delay enabled.
* Fixed an issue where a used stylesheet path would still attempt to load even if no used styles had been picked up for the URL.
* Fixed an issue where browser-specific stylesheets inside HTML comments were getting parsed by our used CSS library.
* Fixed a MU Mode issue where exceptions would not be applied correctly if a query string was present on the home URL if set to show the latest posts.
* Fixed an issue where preloading a JS file by the handle was not loading the minified version when necessary.

= 2.3.3 - 08.28.2024 =
* Added new lazy loading advanced beta options to manage Lazy Elements which will allow for element chains in the DOM to be lazy loaded until they enter the viewport.
* Separated out built-in CSS selector exclusions by URL type for increased performance on single and front pages.
* Optimized plugin logo and other SVG image files.
* Added fetchpriority high attribute automatically on critically preloaded image links.
* Added support for delaying script modules.
* Added additional jQuery sticky JavaScript file to Elementor quick exclusion.
* Added new Delay JS quick exclusions for Fluent Forms and Fluent Forms Pro.
* Integrated get_atts_array utility function into lazyload class to prevent redundancy.
* Fixed an issue where smaller size files were sometimes not being replaced with the minified version for increased performance.
* Fixed an issue where the preload location label was overlapping the input field for certain languages.
* Made adjustments to option management to prevent autoloading of certain options going forward where it is not needed.
* Removed various manual preload types that are no longer supported by most major browsers.

= 2.3.2 - 07.30.2024 =
* Updated CSS parsing library to the latest version (8.6.0) which should help with correctly parsing mathematical operations inside CSS property values.
* Added additional parameter to excluded page builders array for GenerateBlocks and TranslatePress.
* Added additional built-in deferral exclusion for jqueryParams inline script.
* Added Delay JS quick exclusion for the Kadence menu.
* Fixed a MU Mode issue where home page exceptions would not be applied correctly if a query string was present in the requested URL.
* Fixed an undefined array key warning coming from the minify class.
* Fixed a minify error that would show up when a prospective file did not have any content.
* Fixed an issue where having Remove Unused CSS turned on with no stylesheets loading would return a blank screen.
* Fixed a CSS error that would show up when trying to determine the current page ID when the queried post was null.
* Fixed an issue where the CSS class would attempt to retrieve the contents of a stylesheet even if it didn't exist.
* Fixed an issue where minified files would not get picked up by the CDN rewriter.
* Removed unnecessary minify library .git directories from the plugin.
* Minor style adjustments to the plugin UI.
* Updated our staging site license key exception list with additional formats.
* Translation updates.

= 2.3.1 - 06.27.2024 =
* Added new Minify JS and Minify CSS features along with options to exclude specific files from minification and clear generated minified files when necessary.
* UI Updates: What was previously the Assets tab has now been replaced by three more specific tabs, JavaScript, CSS, and Code. The main Script Manager toggle has been moved to Tools. Additional subheaders have also been added throughout to help with organization.
* Added new perfmatters_minify_js filter.
* Added new perfmatters_minify_js_exclusions filter.
* Added new perfmatters_minify_css filter.
* Added new perfmatters_minify_css_exclusions filter.
* Added a REST API exception for Independent Analytics.
* Added additional request parameter for Divi to excluded page builders array.
* Added built-in critical image exclusion for WPML flag images.
* Added Delay JS quick exclusion for Grow for WordPress.
* Updated used CSS function to generate a separate file for each post type archive instead of a single shared stylesheet.
* Fixed an issue that was causing an incorrect root directory to be returned for some environments.
* Fixed an issue with preload and lazyload parent exclusion filters that was preventing them from excluding images correctly in some cases.
* Translation updates.

= 2.3.0 - 05.23.2024 =
* Added a new function to verify the preferred content type from the HTTP header when determining if JSON is being requested. This should improve compatibility with certain hosting providers.
* Added an additional check when removing unused CSS to avoid parsing print-only stylesheets.
* Updated Delay JS quick exclusion for Termageddon + UserCentrics for better compatibility.
* Removed option to disable wlwmanifest link output as that function was deprecated in WordPress 6.3.
* Fixed an issue that was preventing lazy loaded images from displaying when defer inline scripts was enabled.
* Fixed an issue where responsive styles for YouTube preview thumbnails were not printing on certain themes using responsive embeds.
* Fixed an issue with DOMDocument where HTML entities coming from inline styles would display as their encoded values.
* Fixed a missing tooltip on the scan database option.
* Translation updates.

= 2.2.9 - 05.16.2024 =
* Fixed an issue that could cause a conflict with other JS deferral solutions when running at the same time.

= 2.2.8 - 05.16.2024 =
* Added new Defer JavaScript option to Include Inline Scripts.
* Added new option to Separate Block Styles.
* Added additional built-in CSS selector exclusions for Splide.
* Updated Delay JS quick exclusion for Kadence Blocks with additional scripts.
* Updated our staging site license key exception list with additional formats.
* Updated deferral exclusion check to work with entire tag instead of just src URL.
* Moved to printing responsive embed styles for YouTube preview thumbnails in all cases for better compatibility.
* Fixed an issue where the CDN rewrite was not picking up URLs with a relative protocol.
* Fixed an issue where an existing data-wp-strategy attribute would prevent a script from being able to be deferred.
* Fixed an issue where the Script Manager was not giving the right feedback on save when a new line character was showing up in the AJAX response.
* Fixed an issue on the network settings page where incorrect tab content would show up after saving.
* Fixed an issue where the license tab was showing up at the subsite level if the plugin was not network activated in a multisite environment.
* Translation updates.

= 2.2.7 - 04.19.2024 =
* Added new perfmatters_used_css_below filter.
* Added new perfmatters_defer_js_exclusions filter.
* Added new perfmatters_delay_js_fastclick filter.
* Added additional DOMDocument flag to parent exclusion filters for better compatibility.
* Added GiveWP request parameter to excluded page builders array.
* Updated Delay JS quick exclusion for WooCommerce Single Product Gallery with additional scripts to help with zoom and lightbox functionality.
* Updated Delay JS quick exclusion for Cookie Notice with additional scripts.
* Moved Script Manager CSS to stylesheet printed inline instead of from a PHP file.

= 2.2.6 - 03.18.2024 =
* Added new perfmatters_defer_jquery filter.
* Added Delay JS quick exclusion for Monumetric Ads.
* Updated content URL reference to use content_url function instead of constant when generating root directory path.
* Updated local stylesheet URL replace function to be case insensitive.
* Updated new parent exclusion filters to use DOMDocument instead of regex to allow support for targeting images inside nested containers.
* Fixed an issue where certain scripts were not being deferred properly when delay JavaScript option was also enabled.
* Fixed an issue where abnormal image URLs would sometimes generate a warning when trying to parse for image dimensions.
* Translation updates.

= 2.2.5 - 02.29.2024 =
* Added new perfmatters_critical_image_parent_exclusions filter.
* Added new perfmatters_leading_image_parent_exclusions filter.
* Added new Disable Core Fetch option to disable the fetch priority attribute added by WordPress core.
* Added built-in WooCommerce CSS selector exclusion for better compatibility on single product posts.
* Added Breakdance request parameters to excluded page builders array.
* Added a REST API exception for WP Recipe Maker.
* Added Delay JS quick exclusions for Kadence Blocks and Kadence Blocks Pro.
* Added CSS Background Image support for the footer element.
* Fixed an issue where dynamic preload version numbers would sometimes get added to the wrong resource.
* Fixed an issue with certain multilingual setups where the base URL for generated files was incorrect.
* Updated background processing library to the latest version (1.3.0).
* Updated CSS parsing library to the latest version (8.5.1).
* Minor style updates to plugin UI.

= 2.2.4 - 02.05.2024 =
* Added built-in Image Dimensions exclusion for blank placeholder SVGs.
* Added excluded page builders function check to MU plugin file.
* Changed method of retrieving root directory in certain classes for better compatibility with more file structures.
* Fixed PHP warnings coming from local analytics function.

= 2.2.3 - 01.08.2024 =
* Fixed an issue where Mediavine and Modula Slider quick exclusions were not working properly.

= 2.2.2 - 01.07.2024 =
* Fixed PHP warnings coming from certain local analytics setups.
* Translation updates.

= 2.2.1 - 01.04.2024 =
* Removed deprecated Universal Analytics options which are no longer available and renamed remaining script type labels. If you still haven't updated to Google Analytics 4, make sure to create a new profile and input your new measurement ID.
* Added new tools option to Disable Optimizations for Logged In Users.
* Added new perfmatters_leading_image_exclusions filter.
* Added support for targeting figure elements to CSS Background Images.
* Added REST route exception for Litespeed.
* Added and updated Delay JS quick exclusions for Gravity Forms, Mediavine Trellis, Modula Slider, SHE Media Infuse, Thrive Leads, and WP Recipe Maker.
* Added built-in Delay JS exclusion for Divi link options script.
* Added generic customizer request parameter to excluded page builders array.
* Made some adjustments to classes dealing with cache directory files to support non-traditional folder structures such as Bedrock.
* Fixed a PHP warning related to cache URL declaration that would sometimes display for certain types of requests.
* Fixed an issue where picture elements were not getting excluded from lazy loading when fetchpriority high was set on a child image.
* Removed unnecessary script type attribute from our Delay JS inline script.
* Translation updates.

View the full changelog:
[https://perfmatters.io/docs/changelog/](https://perfmatters.io/docs/changelog/)
