Introduction
============

`Resource Registries`_ creates a unique URL each time a CSS or JS file is modified providing a way create unique files without having to rename the original ones.

It also has a feature to concatenate several CSS or JS files to serve less files to the user. But with the way this concatenation is done sometimes the files that can be safely concatenated are not, because the tool just tries to concatenate one file with the previous file. For example:

We have 4 files registered in this order: a.css, b.css, c.css and d.css. If a.css, b.css and d.css are compatible to be concatenated but c.css is not, `Resource Registries`_ will create 3 files: ab.css, c.css and d.css.

This product, patches the way those concatenated files are created to check all previously concatenated files and concatenate the file there. This way, in the previous example, the patch will create 2 files: abd.css and c.css


Installing
==========

Add this product to your buildout, re-run buildout and restart your instance, the patch will be applied automatically.

To remove this feature, just remove the product from your buildout, re-run it and restart the instance.

The product doesn't create an install profile entry in the Products Control Panel and doesn't save anything on the database.


.. _`Resource Registries`: https://pypi.python.org/pypi/Products.ResourceRegistries
