Custom Dropdown menu for Wordpress
==============

Convert regular wp_nav_menu into select element

#Put this into functions.php file

```php
/**
 * SelectBox box menu walker
 * @author  : Dmitry Tokmakov
 * @version : 1.0
 * 
 */

class SelectBox_Menu_Walker extends Walker_Nav_Menu {
        
        function start_el( &$output, $item, $depth = 0, $args = array(), $id = 0 ) {
                global $wp_query;
                $indent = ( $depth ) ? str_repeat( "\t", $depth ) : '';
                
                $classes = empty( $item->classes ) ? array() : (array) $item->classes;
                $selected = in_array('current-menu-item',$classes) ? 'selected="selected"' : '';
                $output .= '<option '.$selected.' value="'.$item->url.'">';
                $output .= $item->title;
        }
        function end_el( &$output, $item, $depth = 0, $args = array() ) {
                $output .= "</option>";
        }
}
```


#Usage

```php
wp_nav_menu( array(
		          'theme_location' => 'mobile',
		          'walker'         => new SelectBox_Menu_Walker(),
		          'items_wrap'     => '<div class="mobile-menu"><form><select onchange="if (this.value) window.location.href=this.value">%3$s</select></form></div>',
	) );

```
