# Beaver Builder Header/Footer Monster

A simple way of using Beaver Builder for headers and footers.

Thanks to the Beaver Builders FaceBook group for inspirtion and ideation...

## Problem Summary

Beaver Builder Pro plugin provides remarkable flexibility in terms of individual page content area, but lacks a way of defining repeating headers and footers. This means people either have to: (1) Manually add BB header and footer rows on a per-page or per-post basis; (2) duplicate pages or posts in the Dashboard that already have the desired layout; (3) utilize a separate means of implementing headers and footers.

* Solution (1) works for a small number of pages (especially with the introduction of global modules), but is not so workable for large sites, or legacy sites.

* Solution (2) is elegant, but not user-friendly for clients, or very blog-friendly.

* Solution (3) means relying on another theme or builder framework that does implement header and footer configuration (whether by means of a builder, or other means). This has the disadvantage of requiring another full set of code (and perhaps another investment), and having to "task-switch" more often between method of layout, rather than than staying within the friendly, and flexible, Beaver Builder Pro system.

## Proposed Solution

The following solution seems as though it would provide a lot of flexibility, while being fairly intuitive, and easy to implement as a third-party developer.

* Create a Beaver Builder child theme based on the BB child theme template.
* In functions.php, create a Global Elements Custom Post Type (CPT) that is designed to appear for admins, but not for normal people. (The user would then use the child theme, telling BB in Settings to use BB on that CPT.)
* Add a meta-box to this CPT (method TBD) that allows one to specify "Use in Header" and "Use in Footer". (Later, this could be expanded to say "Use in Archive", "Use in Single", etc.)
* Copying header.php and footer.php from the main BB theme into the child theme, now add a WP query in each that will pull in the row contents from the appropriate CPT row. 
* We will also have to pull that code through the same shortcode rendering process that BB itself uses when rendering the BB contents in the main loop.
* Find some way of hiding the CPT pages from general users ("hidden" status might work).

We should now have our headers and our footers.

