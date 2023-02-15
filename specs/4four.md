---
testspace:
title: 4four
description: Simple spec
---

{% if page %} {% assign spec = page %} {% endif %}

# {{ spec.title }}
{{ spec.description }}


## [setup]
Setup fixture:
1. This
2. That

{% include cases.md %}

## Workaround

