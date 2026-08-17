=== Clevie Social ===

Author: smartthemes.de
Requires at least: WordPress 6.0
Tested up to: 7.0
Requires PHP: 7.4
License: GNU General Public License v2 or later

A WordPress theme for community sites: a card feed with a vote column, a
full-height left column holding the menu and its own widget area, a right widget
sidebar, and a light and dark mode. On top of that come a magazine template with
list, grid and masonry styles, a layout picker for every single post and page,
typography options, WooCommerce support and a child theme.

The interface language is English. A German translation ships in /languages and
is loaded automatically on a German WordPress install.

== Install ==

1. Go to Appearance → Themes → Add New → Upload Theme.
2. Pick clevie.zip and install it.
3. Click Activate.

== Set up ==

Menu on the left, below the logo
  Appearance → Menus → create a menu → assign the location
  "Primary menu (left column, below the logo)". Sub menus are indented down to
  the third level.

Widgets
  Appearance → Widgets. Three areas are available:
  • Right sidebar – next to the feed, for the community box and widgets.
  • Left sidebar (below the menu) – in the left column, under the primary menu.
  • Footer – full width, above the copyright line.
  An empty area disappears and the content takes over the space.

Logo
  Appearance → Customize → Site Identity → Logo. Without a logo the header shows
  the upvote mark and the site title.

== Customizer: Appearance → Customize → Clevie Social Theme ==

Light / dark
  Default mode for new visitors (light, dark or the system setting) and the
  toggle in the header. A visitor's own choice is stored in their browser.

Colors – light mode / Colors – dark mode
  Eleven colors per mode: page background, cards, second surface, header, left
  sidebar, text, secondary text, borders, accent (the upvote orange), buttons and
  links. Use the toggle in the preview to check the other mode – colors update
  without a reload.

Typography
  Body and heading font from 19 families (system fonts and Google Fonts; Google
  is only contacted when you actually pick one), base font size, line height,
  heading weight, letter spacing, uppercase titles and link underlines.

Layout and sizes
  Default layout for posts, for pages and for the blog, archives and search.
  Widths for the feed, the left column, the right sidebar, the wide layout and
  the magazine area, plus column gap, corner radius and header height. Switches
  for the sticky header, the left column, the full-height left column and the
  "Back to top" button.

Header
  The search field and its placeholder, plus an optional button with its own
  label and link.

Post feed
  Cards or compact, the vote column, featured images and the excerpt length.

Blog and archives
  Each meta element on its own: category, author, date, comment count and
  reading time, plus the reading speed, the label of the read more link and
  breadcrumbs.

Single post
  Featured image, share links, author box, related posts by category or tag,
  links to the previous and next post, and a reading progress bar.

Shop (only with WooCommerce active)
  Products per row, products per page and the sidebar in the shop.

Magazine
  Defaults for all magazine pages, and the option to use the magazine layout for
  the blog, archives and search as well.

Footer
  Number of columns in the widget area and your own text instead of the default
  copyright line.

== The full-height left column ==

Switched on by default and built like the original: the sidebar sticks to the
left edge, runs from the header down to the bottom of the screen and scrolls on
its own while the feed stays put. Menu and widgets sit flat inside it without
card borders, and a click on a widget heading collapses that section – the state
is remembered in the browser. Below 860 pixels the column turns into a drawer
behind the burger icon.

== Layout of single posts and pages ==

The editor has a "Page layout" box on the side with five options:

  • Both sidebars (left and right)
  • Right sidebar only
  • Left column only
  • No sidebars, centered – content keeps the feed width
  • No sidebars, wide – width set under Layout and sizes

"Default" keeps the value from the Customizer, so a landing page can run full
width while the blog keeps its columns. A sidebar only shows up when it holds
widgets. On pages using the Magazine template the "Magazine layout" box controls
the right sidebar.

== Magazine pages ==

1. Pages → Add New. The page content shows up as an intro above the tiles and
   may stay empty.
2. Under Page Attributes → Template pick "Magazine".
3. The "Magazine layout" box appears in the sidebar. Layout, columns, image
   position, right sidebar, category and posts per page can be set for this one
   page. "Default" keeps the Customizer value.

That way several magazine pages can run different styles, for example a wide
masonry page without a sidebar next to a list page with one.

The styles:
  • List – one story per row across the full width. With "Image beside the text"
    the image sits on the left, otherwise above.
  • Grid – tiles of equal height, 2 to 5 across, image on top or on the side.
  • Masonry – staggered tiles in the natural image height, 2 to 5 columns.
Below 1000 pixels the grid drops to two columns, below 620 pixels to one.

== The number in the vote column ==

Without further setup the counter shows the number of comments. A value of your
own goes into the custom field "clevie_score". To wire it up to a voting
plugin, use the filter:

	add_filter( 'clevie_post_score', function ( $score, $post_id ) {
		return (int) get_post_meta( $post_id, 'my_voting_field', true );
	}, 10, 2 );

== WooCommerce ==

Shop, category and product pages inherit the theme colors, corner radius and
fonts, so no extra styling is needed. Products per row and per page come from
the Customizer, and the right sidebar can be switched off for the shop only.
Product gallery zoom, lightbox and slider are enabled.

== Block editor ==

The editor uses the same color palette, font sizes and typography as the front
end, so a draft looks like the finished post.
