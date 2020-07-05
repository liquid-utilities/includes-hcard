---
layout: post
date: 2020-07-05 10:44:25 -0700
title: Includes HCard
excerpt: Example of using `include` keyword to define HCard content
---



This post is a _live_ example of using `include` keyword to define HCard content, [source code][post__includes_hcard__source] is available on GitHub.



{% include modules/includes-hcard/hcard.html name='Jayne Cobb'
                                             organization='Distribution'
                                             phone_type='cell'
                                             phone_number='555-123-4567'
                                             email_type='office'
                                             email_address='name@example.com'
                                             address_street='418 Code St.'
                                             address_extended='Suite 503'
                                             address_locality='Server Request'
                                             address_postal_code='12345'
                                             address_region='ZZ'
                                             address_country_code='USA'
                                             address_country_name='United States of America'
                                             link_label='Web Site'
                                             link_url='https://example.com' %}



[post__includes_hcard__source]: https://github.com/liquid-utilities/includes-hcard/blob/gh-pages/_posts/2020-07-05-includes-hcard.md
