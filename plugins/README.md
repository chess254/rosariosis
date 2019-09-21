# PLUGINS

Place here the Plugins you want to add to RosarioSIS.

## Activate

Activate them via:
_School > Configuration > Plugins_

## Files

- `functions.php`: required. Contains the functions to be automatically loaded by RosarioSIS.
- `config.inc.php`: optional. Included by the `modules/School_Setup/includes/Plugins.inc.php` file when the _Configuration_ link in the plugin listing is clicked.

## Example

You can base your work or reuse any existing plugin. The list of available plugins can be found at https://www.rosariosis.org/add-ons/

## Action hooks

You typically want to register your functions to be hooked on certain actions. The list of actions is available in the [`functions/Actions.php`](https://gitlab.com/francoisjacquet/rosariosis/blob/mobile/functions/Actions.php) file.

For example, to load a specific JS or CSS file in the HTML `<head>` use this code:
```php
// Add our MyPluginHeadLoadJSCSS() function to the Warehouse.php|header_head action.
add_action( 'Warehouse.php|header_head', 'MyPluginHeadLoadJSCSS' );

/**
 * Load JS and CSS in HTML head
 * Load mystylesheet.css & myjavascriptfile.js files.
 *
 * @uses Warehouse.php|header_head action hook
 */
function MyPluginHeadLoadJSCSS()
{
	?>
	<link rel="stylesheet" href="plugins/MyPlugin/css/mystylesheet.css" />
	<script src="plugins/MyPlugin/js/myjavascriptfile.js"></script>
	<?php
}
```