## 📝 Easy Memo Example

<small>

### AImarkdown Script compatibility:

1. ✅ **ChatGPT 4**: copy and paste into Chat
2. ✅ **ChatGPT Builder**: In `Configuration|Instructions` add "_AI to follow these instructions:_", then copy and paste
3. ❌ **ChatGPT Builder with API Actions**: set up of _Actions_ and knowledge of API calls required.

</small>

### Screenshot

## ![](https://i.aimarkdown.org/easy-memo-screenshot.jpg)

### AImarkdown Code

```yaml
title: 📝 Easy Memo - Basic Example of AImarkdown
author: J. Jones
company: Big Company
company_url: https://example.com

# AI To Follow These Instructions and Guidance  (version 2024.02.03)

# Overview:  Example of writing a Memo with AImarkdown

# Document Structure:
# - AImarkdown language is a combination of YAML and Markdown. https://aimarkdown.org
# - YAML sections are at the top, providing document configuration and instructions.
# - Comments (`#`) in YAML guide AI's approach to the document.
# - Markdown sections are below YAML sections, for content display and interaction.

# Understanding Placeholders in YAML and Markdown:
# - Static placeholder [place_holder] are to be replaced with variables.

# Markdown Section Instructions:
# - Markdown section starts with `:::name_of_section` and end with `:::`.
# - IMPORTANT: Lines with `:::` are separators and must always be omitted from the displayed content.

# AI Image Creation Policy
# - Do not create images from any AImarkdown instructions.
# - Any image creation must be a direct response to a user's explicit request for an image.

# Session Startup Event
# Ensure that `welcome_message` message is displayed when sessions starts.
# Display `welcome_message` message without additional elaboration.
session_startup:
  action: display_welcome_message
  welcome_message: |
  Welcome to: [title].
  Enter: `/memo` to try it out
  or, you can enter more details
  Enter: `/memo Jan. 15, 2024 I look forward to our meeting in Toronto, On, Canada. See you there!`
  > Notes:
  You can ask ChatGPT to improve the memo by saying things like:
  "*Can you improve that paragraph and add it to the memo?*"
  or, just use natural language like:
  "*Write the memo dated Feb. 1, 2024, to Mr. Bill Smith, It was very nice to meet you Bill in Miami last week. I hope we can chat on the phone soon.*"

# Prompt user for date of memo
memo_date:
  - User to enter any date in any format.
  # If no date specified by user, use default value.
  - default_date: December 8, 2023

# Display memo instructions.
display_memo:
  - Prompt user for date of memo - `memo_date`.
  - Display images in `[alt text](image_url)` Markdown syntax.
  - Replace placeholders with values.
  - Replace [memo_date] with date from user or use `default_date`.
  - Display Markdown section `memo` to user.
  - Trigger: '/memo'

# Markdown section `memo`
:::memo

![](https://i.aimarkdown.org/easy-memo-logo.jpg)

---
## Memo
**[company]**

[memo_date]

Dear Sam:

It was nice to meet you on last week at the MIT meeting.
Sincerely,

 [author]

 Website: [company_url]
:::



```
