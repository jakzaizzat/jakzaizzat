---
title: "What is SMACSS?"
date: 2017-09-12T20:57:44+08:00
draft: false
---

# Learn SMACSS

Not a framework. It's a way of thinking.

It has 5 categories

* Base
  * Normalize
  * Reset
  * No classes in this page
* Layout ( Major Components )
  * May use ID
  * E.g : Header, sidebar, footer, homepage
* Module ( Minor Components )
  * Classes
  * E.g : Button, Checkout Page
* State
  * Expand module
  * E.g : .btn-primary , .btn-info, . btn-danger
  ```css
  .card {}; /* Module */
  .is-card-hover{}; /* State hover */
  .is-card-expanded{}; /* State on expand */
  ```
* Theme ( Optional )


## Naming Convention

Group in their own module

```css
.video{ };
.video--title{ };
.video--image{ };
.video--meta{ };

```


## Best way to use

Use Sass Preprocessor

```scss

@import 'base';
@import 'utilities';
@import 'layout';
@import 'variables';

@import 'modules/card';

```

Use nesting with drawback

```scss

.card {

  /* Components */
  &--header{ }

  /* Sub Modules */.
  &-animate-left { }

}


```

Learn more on how to SMACSS on [SMACSS.com](https://smacss.com)
