# WP Comment Notes #

**Contributors:** norcross, mordauk

**Website Link:** http://andrewnorcross.com/plugins/

**Donate link:** https://andrewnorcross.com/donate

**Tags:** comments, comment notes, comment

**Requires at least:** 3.0

**Tested up to:** 3.6

**Stable tag:** 1.0.0

**License:** GPLv2 or later

**License URI:** http://www.gnu.org/licenses/gpl-2.0.html


Add custom notes before or after the comment form.

## Description ##

Add custom notes before or after the comment form.


## Installation ##

This section describes how to install the plugin and get it working.

1. Upload `wp-comment-notes` to the `/wp-content/plugins/` directory.
2. Activate the plugin through the 'Plugins' menu in WordPress.
3. Add some text in the fields on a post
4. That's it.


## Frequently Asked Questions ##


### How does it work? ###

Activate the plugin and the metaboxes will appear for posts. Use the filter to add more post type support.

### Does this work on my custom post type? ###

Not by default. Use the `wpcmn_type_support` filter to add it.

**Example:**
```php
function cmm_partial_types( $types ) {

	$types[] = 'MY_CUSTOM_POST_TYPE';

	return $types;
}
add_filter( 'wpcmn_type_support', 'cmm_partial_types' );
```

### Can I add more options to the message type dropdown? ###

Sure can. Use the `wpcmn_before_types` or `wpcmn_after_types` filters.

**Example:**
```php
function cmm_more_before( $before_type ) {

	$extra = '';
	$extra .= '<option value="wild" '.selected( $before_type, 'wild', false ).'>'.__('Wild', 'wpcmn').'</option>';
	$extra .= '<option value="crazy" '.selected( $before_type, 'crazy', false ).'>'.__('Crazy', 'wpcmn').'</option>';

	return $extra;

}
add_filter( 'wpcmn_before_types', 'cmm_more_before' );
```

### I don't like the CSS that comes with it ###

Then write your own. It's a free country. If you *have* to disable it, use the `wpcmn_killswitch` filter.

**Example:**
```php
add_filter( 'wpcmn_killswitch', '__return_true' );
```

### Where is the settings menu? ###

There isn't one. On purpose.

### They don't show up on my theme. ###

Then you're using a theme / framework that has gone cowboy and done it their own way. I can't do anything about that.


## Changelog ##

### 1.0 ###
* First release!


## Upgrade Notice ##

### 1.0 ###
* First release!
