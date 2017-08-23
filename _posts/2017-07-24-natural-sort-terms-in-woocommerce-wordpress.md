---
title: Natural Sort Terms in WooCommerce & WordPress
layout: post
date: 2016-02-24 22:44
image: /assets/images/markdown.jpg
headerImage: false
tag:
- wordpress
- woocommerce
- natural sort
star: true
category: blog
author: konmavrakis
description: Natural Sort Terms with PHP in WordPress
---
If you are looking for a way to natural sort terms/attributes from prodcuts in WooCommerce, or even categories, I've come up with a way to sort everything in natural order. For example, you have attributes in your products that are a list of lets say numbers. Your list might look like this:

* 1
* 2
* 205
* 102
* 110

What will happen, the list will be displayed as (default sorting):

* 1
* 2
* 102
* 110
* 205

In order to sort the list with a natural order like this:

* 1
* 2
* 102
* 110
* 205

You'll simple have to convert the results of ``get_terms()`` to an array and then sort it accordingly.

{% highlight php %}
<?php
$args = array(
  'order' => 'ASC',
  'orderby' => 'name',
  'hide_empty' => true,
);

$filter = get_terms( 'pa_filter', $args );

foreach ( $filter as $term ) {
    $sort_terms[$term->name] = $term;
}

uksort( $sort_terms, 'strnatcmp');

foreach ($sort_terms as $term) {
    //If you want to display an option list
    echo "<option value=" . $term->name . ">" . $term->name . "</option>";
}
{% endhighlight %}