---
layout: post
date: 2020-07-05 10:44:25 -0700
title: FrontMatter HCard
excerpt: Example of using FrontMatter to define HCard content

hcard:
  organization: Distribution
  name: Jayne Cobb

  # email_type: office
  # email_address: name@example.com
  emails:
    - type: office
      address: name@example.com

  # phone_type: cell
  # phone_number: 555-123-4567
  phone_numbers:
    - type: cell
      number: 555-123-4567

    - type: office
      number: 555-987-6543

  address:
    street: 418 Code St.
    extended: Suite 503       ## AKA suite, apartment, etc.
    country_code: USA
    country_name: United States of America
    locality: Server Request  ## AKA city
    region: ZZ                ## AKA state
    postal_code: 12345        ## AKA zip

  # link_label: 'example'
  # link_url: https://example.com
  links:
    - label: 'example one'
      url: https://example.com

    - label: 'example two'
      url: https://example.com

    - label: 'example three'
      url: https://example.com
---



This post is a _live_ example of using FrontMatter to define HCard content, [source code][post__frontmatter_hcard__source] is available on GitHub.



[post__frontmatter_hcard__source]: https://github.com/liquid-utilities/includes-hcard/blob/gh-pages/_posts/2020-07-05-frontmatter-hcard.md
