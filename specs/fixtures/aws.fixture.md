---
testspace:
title: aws.fixture
description: Refer to the [AWS console](https://console.aws.amazon.com/lambda/home?region=us-east-1#/functions/testspace-test-man-auto?tab=configuration). Refer to [JSON to YAML](https://www.json2yaml.com/) for JSON/YAML parameters. 
parent: Fixtures
before:
  name: aws:us-east-1:testspace-test-man-auto
  description: parameter types - string, json, yaml, file
  payload: 
   string: this is a string
   json: {
      "json": [
        "rigid",
        "better for data interchange"
      ],
      "yaml": [
        "slim and flexible",
        "better for configuration"
      ],
      "object": {
        "key": "value",
        "array": [
          {
            "null_value": null
          },
          {
            "boolean": true
          },
          {
            "integer": 1
          }
        ]
      },
      "paragraph": "Blank lines denote\nparagraph breaks\n",
      "content": "Or we\ncan auto\nconvert line breaks\nto save space"
    }
   yaml:
      # <- yaml supports comments, json does not
      # did you know you can embed json in yaml?
      # try uncommenting the next line
      # { foo: 'bar' }

      json:
        - rigid
        - better for data interchange
      yaml:
        - slim and flexible
        - better for configuration
      object:
        key: value
        array:
          - null_value:
          - boolean: true
          - integer: 1
      paragraph: >
        Blank lines denote

        paragraph breaks
      content: |-
        Or we
        can auto
        convert line breaks
        to save space
   file: "@file.json"
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
