---
description: >-
  Learn more about how to configure Specify to generate design tokens and assets
  respecting your company standards.
---

# Configuration

## Introduction

By default, without any [parsers](parsers.md), Specify will return your design data as raw data:

* Design tokens are returned in JSON
* Assets are returned as files

After reading this page, you will be able to setup a tailored transformation pipeline for your design data between Specify and your codebase.

{% embed url="https://www.loom.com/share/e025f385ec2b40acb9819bb85cb0768c" %}

## Examples

### How to run these examples

The following examples are made to be used with the Specify CLI.

Requirements:

* a Specify repository containing design tokens
* a valid personal access token ([Generate one↗](https://specifyapp.com/user/personal-access-tokens))

All examples&#x20;

### Basic

Here's a basic configuration file that targets a Specify repository called `all-design-data` from the `@acme-inc` organization:

{% tabs %}
{% tab title="JavaScript" %}
{% code title=".specifyrc.js" lineNumbers="true" %}
```javascript
module.exports = {
  repository: '@acme-inc/all-design-data',
  personalAccessToken: '<your-personal-access-token>',
  rules: [
    {
      name: 'All design tokens in JSON',
      path: 'design-tokens.json',
      parsers: [],
    },    
  ],
};
```
{% endcode %}
{% endtab %}

{% tab title="JSON" %}
{% code title=".specifyrc.json" lineNumbers="true" %}
```json
{
  "repository": "@acme-inc/all-design-data",
  "personalAccessToken": "<your-personal-access-token>",
  "rules": [
    {
      "name": "All design tokens in JSON",
      "path": "design-tokens.json",
      "parsers": []
    }
  ]
}
```
{% endcode %}
{% endtab %}
{% endtabs %}

The generated `design-tokens.json` has the following content:

{% file src="../.gitbook/assets/design-tokens.json" %}
An example file containing all possible token types pulled from a Specify repository&#x20;
{% endfile %}

### Pull colors as CSS Custom Properties

Now let's update our previous configuration to only pull colors and transform them as CSS Custom Properties in HSL.

{% tabs %}
{% tab title="JavaScript" %}
{% code title=".specifyrc.js" lineNumbers="true" %}
```javascript
module.exports = {
  repository: '@acme-inc/all-design-data',
  personalAccessToken: '<your-personal-access-token>',
  rules: [
    {
      name: 'All design tokens in JSON',
      path: 'colors.css',
      filter: {
        types: ['color']
      },
      parsers: [
        {
          name: 'to-css-custom-properties',
          options: {
            formatTokens: {
              color: 'hsl'
            },
          }
        }
      ],
    },
  ],
};
```
{% endcode %}
{% endtab %}

{% tab title="JSON" %}
{% code title=".specifyrc.json" lineNumbers="true" %}
```json
{
  "repository": "@acme-inc/all-design-data",
  "personalAccessToken": "<your-personal-access-token>",
  "rules": [
    {
      "name": "Colors as CSS Custom Properties",
      "path": "colors.css",
      "filter": {
        "types": ["color"]
      },
      "parsers": [
        {
          "name": "to-css-custom-properties",
          "options": {
            "formatTokens": {
              "color": "hsl"
            }
          }
        }
      ]
    }
  ]
}
```
{% endcode %}
{% endtab %}
{% endtabs %}
