# Child Pages Card Templates

This template is for the [WordPress](https://wordpress.org/) plugin [Child Pages Card](https://wordpress.org/plugins/child-pages-card/).

Anyone can pull request your own template.

Once approved, it will be included in [Child Pages Card](https://wordpress.org/plugins/child-pages-card/), users will be able to select your template, and you will become a contributor to [Child Pages Card](https://wordpress.org/plugins/child-pages-card/).

# Features
* You can freely customize the display of your child pages card via templates.
* Customization is similar to customizing a WordPress theme template.
* You can use the code included here to create template and CSS files and apply them using the three filters below.
```
/** ==================================================
 * Filter for template file of html.
 *
 */
add_filter(
	'child_pages_card_generate_template_html_file',
	function () {
		$wp_uploads = wp_upload_dir();
		$upload_dir = wp_normalize_path( $wp_uploads['basedir'] );
		$upload_dir = untrailingslashit( $upload_dir );
		return $upload_dir . '/tmp/childpagescard-template-html.php';
	},
	10,
	1
);

/** ==================================================
 * Filter for template file of css.
 *
 */
add_filter(
	'child_pages_card_generate_template_css_file',
	function () {
		$wp_uploads = wp_upload_dir();
		$upload_dir = wp_normalize_path( $wp_uploads['basedir'] );
		$upload_dir = untrailingslashit( $upload_dir );
		return $upload_dir . '/tmp/childpagescard-template-css.php';
	},
	10,
	1
);

/** ==================================================
 * Filter for CSS file.
 *
 */
add_filter(
	'child-pages-card_css_url',
	function () {
		$wp_uploads = wp_upload_dir();
		$upload_url = $wp_uploads['baseurl'];
		if ( is_ssl() ) {
			$upload_url = str_replace( 'http:', 'https:', $upload_url );
		}
		$upload_url = untrailingslashit( $upload_url );
		return $upload_url . '/tmp/childpagescard.css';
	},
	10,
	1
);

```

# Requirement

* WordPress Version 5.0 or higher
* Child Pages Card Version 2.00 or higher

# Naming rule

* (php/html/css) One file for each is required.

Template Name:
English notation

File name:
childpagescard-template-html-(template slug name). (php/html)
childpagescard-template-css-(template slug name). (php/css)

# Overview file
* The file `templates.json`, which describes the outline of the template, needs to be edited.

# Usage

| Variable name | Type | Meaning | Filter |
| --- | --- | --- | --- |
| `$hash` | String | A string of one meaning generated from "Page ID". To be added to the end of the class name. |  |
| `$img_pos` | String | Featured image display position: right (right), left (left) | `child_pages_card_img_pos` |
| `$border_pos` | String | Border position: right (right), left (left) | `child_pages_card_border_pos` |
| `$color_width` | Int | Border width | `child_pages_card_color_width` |
| `$color` | String | Border color | `child_pages_card_color` |
| `$t_line_height` | Int | Line height of the title | `child_pages_card_t_line_height` |
| `$d_line_height` | Int | Description line height | `child_pages_card_d_line_height` |
| `$url` | String | Link destination url |  |
| `$img` | bool | Featured image availability |  |
| `$img_url` | String | url of the Featured image |  |
| `$img_width` | Int | Featured image width | `child_pages_card_img_width` |
| `$img_height` | Int | Featured image height | `child_pages_card_img_height` |
| `$title` | String | Title |  |
| `$excerpt` | String | Excerpt |  |

# Author

* [Katsushi Kawamori](https://profiles.wordpress.org/katsushi-kawamori/)

# License

"Child Pages Card Templates" is under [GPLv2 or later](https://www.gnu.org/licenses/old-licenses/gpl-2.0.en.html).

Enjoy making templates!

Thank you!
