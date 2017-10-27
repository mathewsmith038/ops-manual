# Coding Standards
Coding and other standards and practices at Countable Web Productions.
  * This document has arisen out of specific cases where different conventions of developers have caused us to waste time. In some cases, standardizing won't give us this benefit so we won't do it. I currently think double versus single qutoes for strings is such a case.
  * There will be cases where we disagree, but we must all agree that it's more important to be consistent than to follow a particular rule. So, some rules may be arbitrary or even suboptimal, but we follow them so we can stop thinking about them.
  * Coding standards are only necessary when there are multiple ways to express the same logic (more than one program has the same behaviour). In this sense, they're very uninteresting and ideally would be fully automated away. Golang does this correctly by automating formatting as a core feature. This ideal is what we should aspire to so we can save our neurons for more interesting things. To this end, please use editor plugins that auto-format to our standards where possible.
  * In the case a project doesn't currently follow our standards but follows a different one, stick with that project's conventions unless we make a conscious decision to refactor the whole thing. Don't mix conventions.

### No tabs
We are a Python shop, and so observance of pep 8 leads us to use 4 spaces for indentation. We carry this convention to other languages, using 4 spaces for indentation in CSS, HTML, Javacript, etc. We never use the tab character.

### Docker
Please use Docker for any web application project (and other projects where applicable). It should be possible to bring up a new environment by only the following for any of our projects.

```
git clone <repo>
cd <project folder>
cp docker-compose.override.yml.template docker-compose.override.yml
docker-compose up
```

And browsing to http://localhost

Of course, to see anything meaningful you may need to restore a database to your `db` container.


## Python Coding Standards

For Python code, please comply with PEP-8. Editor plugins can automate most of the rules for you.

### Imports

Order imports as follows
```
# Builtins
import os
import sys
import csv

# 3rd Party
import django

# local
import mymodule
```

### Line Length

Lines of up to 119 chars are ok, instead of the default 79 chars. The reason for this is we have higher resolution screens these days and 79 chars is crazy restrictive.


## HTML Standards

Opening and closing tag should have same indentation level, or on the same line. Use 2 spaces per indent level.
Bad:
```
<div>
    <span>
      </span>
  </div>
```
Good:
```
<div>
  <span></span>
</div>
```

Inline styles should be avoided (use CSS class).
Bad:
```
<div style="background:white"></div>
```
Good:
```
<div class="white-bg"></div>
```

Avoid more than one blank line in a row, but content on a new line is fine:
Bad:
```
<div>Hi</div>



<p>and welcome</p>
```
Good:
```
<div>
  Hi
</div>

<p>and welcome</p>
```

## CSS Coding Standards

  * Break the styles into global.css (styles on all pages), layout.css (outer styles), pages.css (specific page and shared components)
  * Rules should generally pass on http://csslint.net/
  * Don't use !important when possible
  * Don't use capital letters or underscores. Use dashes and lowerase.
 
## Javascript Coding Standards

For javascript, use the Prettier autoformatter and standard. https://github.com/prettier/prettier