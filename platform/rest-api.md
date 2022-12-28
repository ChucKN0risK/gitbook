---
description: >-
  The Specify API lets you extend Specify functionalities beyond what we provide
  out of the box.
---

# REST API

## Introduction

The Specify API is based on REST structure. We support authentication via access tokens. Requests are made via HTTP endpoints with clear functions and appropriate response codes. Endpoints allow you to request design tokens and assets from a Specify repository.

Specify's REST API is useful if you want to use design data coming from Specify through custom scripts like a Figma plugin or a [Raycast script](https://www.raycast.com/).

In short, our REST API helps you request design data through HTTP requests. Like with our [CLI](cli.md) you can use parsers to transform design data.

However, you cannot directly generate files using the REST API as it only returns text. You'll have to write custom scripts to generate design files (e.g., `colors.css`).

To sum things up, to generate files from Specify (e.g., `colors.css` or `icon.svg`) containing design tokens or assets use the [CLI](cli.md) or our [GitHub application](https://specifyapp.com/developers/github).
