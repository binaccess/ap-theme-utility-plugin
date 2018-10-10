# AP Theme Utility
A Plugin to import the WordPress site demo content.

# Installation
- Download a updated copy of AP Theme Unitliy plugin from https://wordpress.org/plugins/ap-theme-utility-plugin/
- Extract the downloaded plugin zip file.
- Copy the Extracted copy of folder 'ap-theme-utility-plugin' to 'wp-content/plugins/'
- Login to your WordPress admin Dashboard - Plugins
- Activate the 'AP Theme Utility' plugin.

## Configuring the Demo
Next generate the necessary demo content( Customizer Settings, WordPress Content, Widet Contents ) using the following plugins
- [Customizer Export/Import](https://wordpress.org/plugins/customizer-export-import/),
- [Widget Importer & Exporter](https://wordpress.org/plugins/widget-importer-exporter/),
- [WordPress Importer](https://wordpress.org/plugins/wordpress-importer/)

Now, Integrate the demo installation in your theme by,

```
<?php
	if(class_exists('APTU_Class')) :

		$demos = array(
			'demo-one' => array(
				'title' => __('Demo One', 'theme-slug'),
				'name' => 'demo-one',
				'screenshot' => get_template_directory_uri().'/path/to/demo-one/screen.png',
				'home_page' => 'front-page',
				'menus' => array(
					'Main Menu' => 'primary',
					'Footer Menu' => 'footer-menu',
				)
			),
		);

		$demoimporter = new APTU_Class( $demos, $demo_dir='path\to\demo\directory' );
	endif;
```

### Explanation:
