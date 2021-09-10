=== Bootstrap 5 Sass Template for Visual Studio Code ===

Version: Bootstrap 5.1.1
Contributors: The bootScore Contributors
License: MIT License
License URI: https://github.com/bootscore/bootstrap-5-sass-template-for-vscode/blob/main/LICENSE

== Description ==

Create and compile your own bootstrap.min.css with this template. Compiled CSS can be used in bootScore theme. Copyright 2021 Bastian Kreiter.

== Documentation ==

https://bootscore.me/documentation/custom-bootstrap-min-css/

== General Usage ==

1. Download file and unzip
2. Download and install Visual Studio Code https://code.visualstudio.com/download
3. Install Live Sass Compiler Extension https://marketplace.visualstudio.com/items?itemName=ritwickdey.live-sass
4. Open Visual Studio Code and open file folder
5. Open index.html in browser
6. Edit variables in folder /dist/css/bootstrap.scss. Available variables can be found in folder /scss/_variables.scss
7. Save file
8. Klick "Watch Sass" in the blue banner in VSCode window
9. Enjoy your new Bootstrap

== Usage in bootScore-child ==

1. Copy your generated bootstrap.min.css, bootstrap.min.css.map (optional), bootstrap.scss (optional, in case you want to edit later, store a copy of it) in folder /css/lib/ in child theme.
2. Insert following snippet in child-theme's functions.php:

// Overide bootstrap.min.css in child-theme
function bootscore_replace_bootstrap() {

    // Dequeue parent-theme bootstrap.min.css
    wp_dequeue_style( 'bootstrap' );
    wp_deregister_style( 'bootstrap' );

    // Enqueue new bootstrap.min.css in child-theme
    wp_enqueue_style( 'child-theme-bootstrap', get_stylesheet_directory_uri() .'/css/lib/bootstrap.min.css' , array('parent-style'));
}
add_action( 'wp_enqueue_scripts', 'bootscore_replace_bootstrap', 20 );

3. Enjoy your new bootScore


== Changelog ==

    = September 07 2021 = 
    
        * Bootstrap 5.1.1

    = August 05 2021 = 
    
        * Bootstrap 5.1.0
        * added navbar offcanvas example

    = June 23 2021 = 
    
        * Bootstrap 5.0.2
        * updated index.html

    = May 14 2021 = 
    
        * Bootstrap 5.0.1

    = May 06 2021 =
        
        * Bootstrap 5.0.0

    = April 26 2021 = 
    
        * Bootstrap v5.0.0-beta3
