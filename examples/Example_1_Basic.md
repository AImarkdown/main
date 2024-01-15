## Simple Memo Example

> Description: Start of a basic `Memo Writer` app

- type `/memo` to write a Memo

- Code:

- See actual ChatGPT session at:
  https://chat.openai.com/share/965fa701-5179-4a37-8946-a2b009819e4a

#### Screenshot

![](images/Example_1_Basic.png)

## Code

```yaml
title: Easy Memo ~ Basic Example of AImarkdown
author: J. Jones
company: Big Company Name
url: https://example.com


# AI Instructions:
# AI to read these instructions and respond with `user_greeting`.
# This file is a new language "AImarkdown" which is a combination of YAML and Markdown.
# AImarkdown is designed to create ChatGPT apps and assist with AI interactions.
# Markdown sections start with tag `:::name_of_section` and end with tag `:::`.
# Ignore any lines starting with `:::` when displaying Markdown sections.

user_greeting: |
  "Welcome! **[title]**.
  **Enter**: `/memo` to try it out


display_memo:
  - display section ':::memo' with images to user
  - replace placeholders with values
  - replace [[today]] with today's date
  - Trigger: '/memo'

:::Memo

![](https://i.aimarkdown.org/logo.png)

---
# MEMO

[[today]]
## [company]

Dear Sam:

It was nice to meet you on [[today]].

Sincerely,
 [author]

Website: [url]
:::

```
