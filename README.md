wp-select-menu
==============

Convert regular wp_nav_menu into select element


#Usage

```php
wp_nav_menu( array(
		          'theme_location' => 'mobile',
		          'walker'         => new SelectBox_Menu_Walker(),
		          'items_wrap'     => '<div class="mobile-menu"><form><select onchange="if (this.value) window.location.href=this.value">%3$s</select></form></div>',
	) );

```
