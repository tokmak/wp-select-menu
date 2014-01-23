wp-select-menu
==============

Convert regular wp_nav_menu into select element


#Usage

```php
wp_nav_menu( array(
		          'theme_location' => 'mobile',
		          'walker'         => new Walker_Nav_Menu_Dropdown(),
		          'items_wrap'     => '<div class="mobile-menu"><form><select onchange="if (this.value) window.location.href=this.value">%3$s</select></form></div>',
	) );

```
