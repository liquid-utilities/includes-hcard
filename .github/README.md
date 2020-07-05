# Includes Hcard
[heading__top]:
  #includes-hcard
  "&#x2B06; Liquid utility that builds HCard compatible HTML"


Liquid utility that builds HCard compatible HTML


## [![Byte size of Includes Hcard][badge__main__includes_hcard__source_code]][includes_hcard__main__source_code] [![Open Issues][badge__issues__includes_hcard]][issues__includes_hcard] [![Open Pull Requests][badge__pull_requests__includes_hcard]][pull_requests__includes_hcard] [![Latest commits][badge__commits__includes_hcard__main]][commits__includes_hcard__main] [![includes-hcard Demos][badge__gh_pages__includes_hcard]][gh_pages__includes_hcard]
main
------


- [:arrow_up: Top of Document][heading__top]

- [:building_construction: Requirements][heading__requirements]

- [:zap: Quick Start][heading__quick_start]

  - [:memo: Edit Your ReadMe File][heading__your_readme_file]
  - [:fountain: Your Layout File][heading__your_layout_file]
  - [:floppy_disk: Commit and Push][heading__commit_and_push]

- [&#x1F9F0; Usage][heading__usage]

- [&#x1F5D2; Notes][heading__notes]

- [:card_index: Attribution][heading__attribution]

- [:balance_scale: Licensing][heading__license]


------



## Requirements
[heading__requirements]:
  #requirements
  "&#x1F3D7; Prerequisites and/or dependencies that this project needs to function properly"


This repository depends upon [Jekyll][jekyll_rb__home] which is supported by [GitHub Pages][github_docs__github_pages__jekyll], further details about setup can be found from [documentation][jekyll_rb__github_pages] published by the Jekyll maintainers regarding GitHub Pages.


___


## Quick Start
[heading__quick_start]:
  #quick-start
  "&#9889; Perhaps as easy as one, 2.0,..."


This repository encourages the use of Git Submodules to track dependencies


**Bash Variables**


```Bash
_module_name='includes-hcard'
_module_https_url="https://github.com/liquid-utilities/includes-hcard.git"
_module_base_dir='_includes/modules'
_module_path="${_module_base_dir}/${_module_name}"
```


**Bash Submodule Commands**


```Bash
cd "<your-git-project-path>"

git checkout gh-pages
mkdir -vp "${_module_base_dir}"

git submodule add\
 -b main --name "${_module_name}"\
 "${_module_https_url}" "${_module_path}"
```


### Your ReadMe File
[heading__your_readme_file]:
  #your-readme-file
  "&#x1F4DD; Suggested additions for your ReadMe.md file so everyone has a good time with submodules"


Suggested additions for your _`ReadMe.md`_ file so everyone has a good time with submodules


```MarkDown
Clone with the following to avoid incomplete downloads


    git clone --recurse-submodules <url-for-your-project>


Update/upgrade submodules via


    git submodule update --init --merge --recursive
```


### Your Layout File
[heading__your_layout_file]:
  #your-layout-file
  "&#x26F2; "


Add an include statement, _`{% include modules/includes-hcard/hcard.html %}`_, within the chosen Layout file, for example if utilizing the [`minima/jekyll`](https://github.com/jekyll/minima) theme modifications may be similar to...


**`_layouts/default.html`**


```HTML
---
layout: default
license: MIT
source: https://raw.githubusercontent.com/jekyll/minima/v2.0.0/_layouts/default.html
---
<!DOCTYPE html>
<html lang="{{ page.lang | default: site.lang | default: "en" }}">

  {% include head.html %}

  <body>

    {% include header.html %}

    <main class="page-content" aria-label="Content">
      <div class="wrapper">
        {{ content }}
      </div>

      {% if page.hcard %}
        <div class="contacts">
          {% include modules/includes-hcard/hcard.html %}
        </div>
      {% endif %}
    </main>

    {% include footer.html %}

  </body>

</html>
```


------


### Commit and Push
[heading__commit_and_push]:
  #commit-and-push
  "&#x1F4BE; It may be just this easy..."


```Bash
git add .gitmodules
git add "${_module_path}"


## Add any changed files too


git commit -F- <<'EOF'
:heavy_plus_sign: Adds `liquid-utilities/includes-hcard#1` submodule



**Adds**


- `.gitmodules`, tracks submodules AKA Git within Git _fanciness_

- `README.md`, updates installation and updating guidance

- `_modules_/includes-hcard`, Liquid utility that builds HCard compatible HTML

- `_layouts/default.html`, modified default layout from `jekyll/minima` theme
EOF


git push origin gh-pages
```


**:tada: Excellent :tada:** your project is now ready to begin unitizing code from this repository!


------


## Usage
[heading__usage]:
  #usage
  "&#x1F9F0; How to utilize code from this repository within another project"


First option, utilize FrontMatter configurations for the selected layout...


[**`_posts/2020-07-05-frontmatter-hcard`**][post__includes_hcard__source]


```MarkDown
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



... Post content...
```


Above commented FrontMatter configurations are able to be used instead of _list_/_object_ like blocks. A [_live_ example][post__frontmatter_hcard__demo] of output from using FrontMatter to define HCard content is available thanks to GitHub Pages.


Either `name` **or** `organization` configurations are required, all other FrontMatter configurations are optional.


------


Second option, include the `hcard.html` file within an individual post or page using include named parameters instead of FrontMatter...


[**`_posts/2020-07-05-includes-hcard.md`**][post__includes_hcard__source]


```MarkDown
---
layout: post
date: 2020-07-05 10:44:25 -0700
title: Includes HCard
excerpt: Example of using `include` keyword to define HCard content
---



... Post content...



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
```


**Notice**, new-lines between parameters in above example are for readability and may need to be replaced with spaces. A [_live_ example][post__includes_hcard__demo] of output from using `include` keyword to define HCard content is available thanks to GitHub Pages.


**Example Output (snip)**


```HTML
<div id="hcard-jayne-cobb" class="h-card vcard">
  <div class="p-org org">Distribution</div>
  <div class="p-name fn">Jayne Cobb</div>

  <div class="p-tel tel">
    <span class="type">cell</span>: <a class="value">555-123-4567</a>
  </div>

  <div class="u-email email">
    <span class="type">office</span>: <a class="value" href="mailto:name@example.com">name@example.com</a>
  </div>

  <div class="p-adr adr">
    <span class="p-street-address street-address">418 Code St.</span>
    <span class="p-extended-address extended-address">Suite 503</span>
    <span class="p-locality locality">Server Request</span>
    <span class="p-region region">ZZ</span>
    <span class="p-postal-code postal-code">12345</span>
    <span class="p-country-name usa" title="United States of America">USA</span>
  </div>

  <div>
    <a class="url fn org" href="https://example.com">Web Site</a>: <small>https://example.com</small>
  </div>
</div>
```

___


## Notes
[heading__notes]:
  #notes
  "&#x1F5D2; Additional things to keep in mind when developing"


This repository may not be feature complete and/or fully functional, Pull Requests that add features or fix bugs are certainly welcomed.


- [Fork][includes_hcard__fork_it] this repository to an account that you have write permissions for.

- Add remote for fork URL. The URL syntax is _`git@github.com:<NAME>/<REPO>.git`_...


```Bash
cd ~/git/hub/liquid-utilities/includes-hcard

git remote add fork git@github.com:<NAME>/includes-hcard.git
```


- Commit your changes and push to your fork, eg. to fix an issue...


```Bash
cd ~/git/hub/liquid-utilities/includes-hcard


git commit -F- <<'EOF'
:bug: Fixes #42 Issue


**Edits**


- `<SCRIPT-NAME>` script, fixes some bug reported in issue
EOF


git push fork main
```


> Note, the `-u` option may be used to set `fork` as the default remote, eg. _`git push fork main`_ however, this will also default the `fork` remote for pulling from too! Meaning that pulling updates from `origin` must be done explicitly, eg. _`git pull origin main`_


- Then on GitHub submit a Pull Request through the Web-UI, the URL syntax is _`https://github.com/<NAME>/<REPO>/pull/new/<BRANCH>`_


> Note; to decrease the chances of your Pull Request needing modifications before being accepted, please check the [dot-github](https://github.com/liquid-utilities/.github) repository for detailed contributing guidelines.


___


## Attribution
[heading__attribution]:
  #attribution
  "&#x1F4C7; Resources that where helpful in building this project so far."


- [GitHub -- `github-utilities/make-readme`](https://github.com/github-utilities/make-readme)

- [Wikipedia -- HCard](https://en.wikipedia.org/wiki/HCard)

- [Wikipedia -- VCard](https://en.wikipedia.org/wiki/VCard)

- [XFront -- `microformats/hCard`](https://www.xfront.com/microformats/hCard.html)


___


## License
[heading__license]:
  #license
  "&#x2696; Legal side of Open Source"


```
Liquid utility that builds HCard compatible HTML
Copyright (C) 2020 S0AndS0

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU Affero General Public License as published
by the Free Software Foundation, version 3 of the License.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Affero General Public License for more details.

You should have received a copy of the GNU Affero General Public License
along with this program.  If not, see <https://www.gnu.org/licenses/>.

```


For further details review full length version of [AGPL-3.0][branch__current__license] License.



[branch__current__license]:
  /LICENSE
  "&#x2696; Full length version of AGPL-3.0 License"


[badge__commits__includes_hcard__main]:
  https://img.shields.io/github/last-commit/liquid-utilities/includes-hcard/main.svg

[commits__includes_hcard__main]:
  https://github.com/liquid-utilities/includes-hcard/commits/main
  "&#x1F4DD; History of changes on this branch"


[includes_hcard__community]:
  https://github.com/liquid-utilities/includes-hcard/community
  "&#x1F331; Dedicated to functioning code"

[includes_hcard__gh_pages]:
  https://github.com/liquid-utilities/includes-hcard/tree/
  "Source code examples hosted thanks to GitHub Pages!"

[badge__gh_pages__includes_hcard]:
  https://img.shields.io/website/https/liquid-utilities.github.io/includes-hcard/index.html.svg?down_color=darkorange&down_message=Offline&label=Demo&logo=Demo%20Site&up_color=success&up_message=Online

[gh_pages__includes_hcard]:
  https://liquid-utilities.github.io/includes-hcard/index.html
  "&#x1F52C; Check the example collection tests"

[issues__includes_hcard]:
  https://github.com/liquid-utilities/includes-hcard/issues
  "&#x2622; Search for and _bump_ existing issues or open new issues for project maintainer to address."

[includes_hcard__fork_it]:
  https://github.com/liquid-utilities/includes-hcard/
  "&#x1F531; Fork it!"

[pull_requests__includes_hcard]:
  https://github.com/liquid-utilities/includes-hcard/pulls
  "&#x1F3D7; Pull Request friendly, though please check the Community guidelines"

[includes_hcard__main__source_code]:
  https://github.com/liquid-utilities/includes-hcard/
  "&#x2328; Project source!"

[badge__issues__includes_hcard]:
  https://img.shields.io/github/issues/liquid-utilities/includes-hcard.svg

[badge__pull_requests__includes_hcard]:
  https://img.shields.io/github/issues-pr/liquid-utilities/includes-hcard.svg

[badge__main__includes_hcard__source_code]:
  https://img.shields.io/github/repo-size/liquid-utilities/includes-hcard


[post__includes_hcard__source]:
  https://github.com/liquid-utilities/includes-hcard/blob/gh-pages/_posts/2020-07-05-includes-hcard.md

[post__includes_hcard__demo]:
  https://liquid-utilities.github.io/includes-hcard/2020/07/07/includes-hcard.md


[post__frontmatter_hcard__source]:
  https://github.com/liquid-utilities/includes-hcard/blob/gh-pages/_posts/2020-07-05-frontmatter-hcard.md

[post__frontmatter_hcard__demo]:
  https://liquid-utilities.github.io/includes-hcard/2020/07/07/frontmatter-hcard.md


[jekyll_rb__home]:
  https://jekyllrb.com/
  "Jekyll home page"

[jekyll_rb__github_pages]:
  https://jekyllrb.com/docs/github-pages/
  "Jekyll documentation for GitHub Pages setup"

[github_docs__github_pages__jekyll]:
  https://docs.github.com/en/github/working-with-github-pages/setting-up-a-github-pages-site-with-jekyll
  "GitHub Pages documentation on Jekyll setup"
