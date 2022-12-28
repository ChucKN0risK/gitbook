---
description: >-
  The Specify CLI helps you pull design tokens and assets from Specify right
  from your terminal.
---

# CLI

### Introduction

Use the Specify CLI to integrate Specify in your workflow.

You can use the Specify CLI to:

* Pull your design tokens in the right format using parsers
* Test your configuration before using it in a GitHub repository
* Sync a Specify repository

### Installation

Install `@specifyapp/cli` via npm or Yarn.

{% tabs %}
{% tab title="NPM" %}
```bash
npm install -g @specifyapp/cli
```
{% endtab %}

{% tab title="Yarn" %}
```bash
yarn global add @specifyapp/cli
```
{% endtab %}
{% endtabs %}

### Commands

#### Sync

Sync a Specify repository to update its design tokens and assets.

```bash
specify sync [flags]
```

#### Init

Initialize a Specify configuration tailored for a specific output format. See all configuration templates.

```bash
specify init
```

#### Pull

Pull design tokens and assets from a Specify repository. 

```bash
specify pull [flags]
```


### Flags
Flags are parameters you can pass while launching the command. All of these parameters are optional if you use a config file.
