# WPPublicAssetsJSCSS
WordPress Public JS and CSS 

```PHP
 // https://woocommerce.wp-a2z.org/oik_api/wc_enqueue_js/
 // https://wp-kama.com/plugin/woocommerce/function/wc_enqueue_js
 wc_enqueue_js();
```

```PHP
// Add public assets no framework or boilerplate
// JS / script
add_action( 'wp_enqueue_scripts', 'myplugin_enqueue_script_public' );
function myplugin_enqueue_script_public() {

	/*
	 wp_enqueue_script(
	   string           $handle,
	   string           $src = '',
	   array            $deps = array(),
	   string|bool|null $ver = false,
	   bool             $in_footer = false
	 )
	*/

	 $src = plugin_dir_url( __FILE__ ) .'public/js/example-public.js';
   
	 wp_enqueue_script( 'myplugin-public', $src, array(), null, false );
}
```

```PHP
// Add public assets no framework or boilerplate
// CSS / style
add_action( 'wp_enqueue_scripts', 'myplugin_enqueue_style_public' );
function myplugin_enqueue_style_public() {

	/*
	  wp_enqueue_style(
	    string           $handle,
	    string           $src = '',
	    array            $deps = array(),
	    string|bool|null $ver = false,
	    string           $media = 'all'
	  )
	*/

	$src = plugin_dir_url( __FILE__ ) .'public/css/example-public.css';

	wp_enqueue_style( 'myplugin-public', $src, array(), null, 'all' );
}
```
