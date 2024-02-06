- [What is AImarkdown?](#what-is-aimarkdown)
- [Getting Started:](#getting-started)
  - [ChatGPT 4](#chatgpt-4)
  - [ChatGPT Builder](#chatgpt-builder)
  - [Learn by Example](#learn-by-example)
- [Markdown Language Help](#markdown-language-help)
- [YAML Language Help](#yaml-language-help)
- [Language Documentation Help](#language-documentation-help)
  - [Suggested Style Guide](#suggested-style-guide)
    - [YAML Section Use of Comments](#yaml-section-use-of-comments)
  - [Guide to Using Quotes and Backticks](#guide-to-using-quotes-and-backticks)
    - [Proximity of Comments and Instructions](#proximity-of-comments-and-instructions)
    - [Indents](#indents)
    - [Line spacing](#line-spacing)
    - [Variables:](#variables)
  - [Syntax and Structure](#syntax-and-structure)
    - [YAML Sections](#yaml-sections)
    - [Multiple AIMD sections, can be used , use terminator `...`](#multiple-aimd-sections-can-be-used--use-terminator-)
    - [Markdown Sections](#markdown-sections)
    - [AI Instructions](#ai-instructions)
    - [Placeholders](#placeholders)
    - [Improperly Formatted YAML](#improperly-formatted-yaml)
    - [Triggers](#triggers)
  - [Extensions and Customization](#extensions-and-customization)
- [Anatomy of a AImarkdown File](#anatomy-of-a-aimarkdown-file)
  - [Example File memo.aimd](#example-file-memoaimd)
  - [Explanation](#explanation)
    - [Metadata](#metadata)
    - [AI Instructions and guidance](#ai-instructions-and-guidance)
    - [Variables, functions, code and specific instructions](#variables-functions-code-and-specific-instructions)
    - [Markdown section](#markdown-section)
- [ChatGPT 4 vs. ChatGPT Builder.](#chatgpt-4-vs-chatgpt-builder)
- [Developer TIPS](#developer-tips)
  - [Using Visual Studio Code (VS Code)](#using-visual-studio-code-vs-code)
  - [iPhone as Developer Platform](#iphone-as-developer-platform)

---

# What is AImarkdown?

> version 0.6

- AImarkdown (`.aimd` file) is a specialized formatting language designed to configure AI behavior and user interactions.
- It combines YAML for configuration and instructions with Markdown for content, allowing for both technical settings and user-facing text to coexist in a single document.
- Aimed at both programmers and non-programmers, AImarkdown facilitates the creation of interactive AI applications by providing a structured yet readable format for defining AI responses, behaviors, and more.
- It supports conditional logic, session management, and other complex functionalities through simple, declarative syntax, making it accessible for a wide range of users to create dynamic and interactive AI-powered content.
- It is designed to facilitate AI interactions and create AI-powered applications for ChatGPT 4.

It extends traditional YAML and Markdown with AI-specific constructs.

# Getting Started:

- **Requirements:** Any device capable of running ChatGPT 4 or ChatGPT Builder.
- **Code Editor:** You can create AImarkdown apps in any text editor, even as an email message.
- **Easy Backup:** Backup complete apps and data in single text file or an email message.
- **Online Editor and Validator:** [https://validator.aimarkdown.org/](https://validator.aimarkdown.org/).

**Installing and running your AImarkdown App:**

> It couldn't be any easier.

### ChatGPT 4

1. Paste AImarkdown text into any ChatGPT session, **_or_**
2. Upload a AImarkdown text file to ChatGPT

### ChatGPT Builder

1. Under the `Configuration` tab, in the `Instructions` box paste the AImarkdown text. (Do not upload a text file).
2. In the `Instructions` box, above the AImarkdown text, add some instructions.

### Learn by Example

- One of the best ways to learn AImarkdown is to explore and tryout some examples.
- Examples on Github: https://github.com/AImarkdown/main/tree/main/examples

# Markdown Language Help

- Markdown is a lightweight markup language that you can use to add formatting elements to plaintext text documents. Created by John Gruber in 2004, Markdown is now one of the world’s most popular markup languages. As a matter of fact, ChatGPT uses standard Markdown to format responses.
- Reference: https://www.markdownguide.org

# YAML Language Help

- YAML™ (rhymes with “camel”) is a human-friendly, cross language, Unicode based data serialization language designed around the common native data types of dynamic programming languages. It is broadly useful for programming needs ranging from configuration files to internet messaging to object persistence to data auditing and visualization.
- Reference: YAML specification v1.2.2
- YAML Cheat Sheet: https://www.coderstool.com/yaml-cheat-sheet

**IMPORTANT**

- AI can often overlook errors and typos, but it is far better to make your `.aimd` files as error-free and clear as possible

- Free online AImarkdown Editor and Validator: https://validator.aimarkdown.org

# Language Documentation Help

Finding the right balance for AI instructions in your files can indeed be a bit of a trial and error process. Since AI systems like this one can interpret and act on a variety of instructions, it often depends on the complexity of the task and the desired outcome. Starting with minimal instructions is a good approach. It allows you to gauge the AI’s understanding and then iteratively add more details or specificity as needed.

It’s also about striking a balance between over-specifying, which can limit the AI’s flexibility, and under-specifying, which might lead to ambiguous results. Experimentation and adjustments is required, especially since AImarkdown is not natively supported by Chat GPT 4.

## Suggested Style Guide

- talk about variable names ??? xxx
- etc.

### YAML Section Use of Comments

**YAML** section

- comments are `#` and should occur on their own line starting with `#`
- comments provide instructions and guidance to AI, they are **not** ignored.

## Guide to Using Quotes and Backticks

This guide provides best practices for using backticks (` ` `), single quotes (`'`), and double quotes (`"`) in AIMarkdown, with examples for clarity.

**1. Backticks (`)**

- **Use Case**: For inline code, command names, file paths, or technical terms.
- **Best Practice**: Enclose text that should be displayed in a monospaced font.
- **Example**:
  ```
  `user_greeting`
  ```
  ```
  - Display `bookmark_summary_header` `
  ```

**2. Single Quotes (`'`)**

- **Use Case**: For simple string literals or literal characters.
- **Best Practice**: Use for strings to be interpreted literally, without special characters.
- **Example**:
  ```yaml
  user_greeting: `Welcome to Chat BookMarker`
  ```

**3. Double Quotes (`"`)**

- **Use Case**: For string literals with special characters or formatting.
- **Best Practice**: Use when strings contain special characters or require escape sequences.
- **Example**:
  ```yaml
  error_message: "Line 10: Unexpected character found."
  ```

Choosing the correct type of quotation mark based on the context and content is crucial for effective communication in AIMarkdown. Consistent and appropriate usage ensures clarity for both AI interpretation and human readability.

### Proximity of Comments and Instructions

It appears that proximity may be important in the AMD file, especially without native support.

In AImarkdown, placing instructions directly within the YAML structure usually works best for straightforward, rule-based tasks, as YAML is designed for configuration and data representation. However, for more nuanced guidance or explanations, comments within the YAML (#) can be more effective, as they allow for more detailed instructions without interfering with the YAML's data structure.

### Indents

- are two spaces and in the YAML section
- as a matter of fact, traditional YAML demands this

### Line spacing

- Metadata should occur at the top of the document
- Separate parts of YAML with single line
- Separate Markdown sections with a double line

- Examples

Metadata:

```YAML
author: Joe Smith
```

### Variables:

- Variables should be long enough to express meaning
- spaces are shown as underscore: `_`
- Sentence case with period for longer string variables
- Example:

```YAML
previous_AI_message: ???
```

## Syntax and Structure

### YAML Sections

- YAML sections are placed at the top of the document.
- Used for metadata like title, description, author, and version information.
- Example:
  ```yaml
  title: AI App
  description: A description of the AI app.
  ```

### Multiple AIMD sections, can be used , use terminator `...`

- AImarkdown files can contain more than one AIMD section.
-

### Markdown Sections

- Follows the YAML sections.
- Standard Markdown syntax is used.
- Special tags `:::name_of_section` mark the start and `:::` the end of a section.

### AI Instructions

- Enclosed in a dedicated YAML section.
- Define how the AI should interpret and respond to the content.
- Example:
  ```yaml
  AI_Instructions:
    - previous_AI_message: reference the last AI message
    - summarize_previous_AI_message: summarize in one sentence.
  ```

### Placeholders

- Used within Markdown sections but refer to YAML section for variables.

**TYPES of Placeholders**

1. **Static** uses `[...]`
2. **Dynamic** uses `[[...]]`
3. **Run Code** uses `[[[...]]]`

**Examples:**

- `*Note*: [[bookmark_note]]`
- ???

### Improperly Formatted YAML

If YAML is not proper formatted inside of a AImarkdown file it can cause AI to not follow the instructions. Rather that alert the developer that there is a problem, AI will just try to make the best of it, and continue on.

> For example

> If the "Welcome" message (greeting) is not valid YAML, the application will continue on without displaying
> any greeting at all. The functionality of the application will work, but without the greeting.

You can use the online **AImarkdown Editor and Validator**

- https://validator.aimarkdown.org

When incorporating YAML into AImarkdown for configuring AI behavior, it's crucial to ensure the YAML is correctly formatted according to standard syntax and indentation rules. However, it's important to recognize how AI will handle YAML formatting issues:

- **Robust Interpretation**: AI systems are designed to interpret and act upon instructions to the best of their ability, even when faced with improperly formatted YAML. This robustness aims to maintain a smooth user experience.

- **Overlooking Errors**: If the AI encounters YAML errors or ambiguous instructions, it might overlook these issues and proceed with the interaction by defaulting to generic responses or the most logical action based on the context. Notably, the AI may not explicitly notify the user of the formatting errors, instead opting to carry on with the task at hand.

- **User Experience Priority**: This behavior underscores a priority for continuity and user engagement. The AI attempts to fulfill the user's request or continue the dialogue, prioritizing the interaction's flow over halting for corrections.

- **Importance of Correct Formatting**: Proper YAML formatting is essential for precise AI behavior configuration. While AI can often navigate minor issues, significant errors in YAML structure might lead to unintended behavior or the omission of specific configured actions, such as displaying a customized welcome message.

- **Validation and Testing**: It's recommended to validate YAML formatting and test the configurations in a controlled environment before implementation. This ensures that the AI behaves as intended, even as it demonstrates flexibility in handling inputs.

This approach by AI, to interpret instructions flexibly and continue providing assistance, highlights the importance of clear and correct configuration while also emphasizing the AI's design to be as helpful and adaptive as possible.

### Triggers

- refer to user prompts.
- Specific commands or phrases that activate certain AI functions.
- Specified in the YAML section.
- Keystoke or text example:

```yaml
trigger: /bm Activates the bookmark function
```

- Event example:

```yaml
trigger: When ChatGPT sessions starts.
```

## Extensions and Customization

- AIMD can be extended with custom tags and placeholders.
- Users can define their own triggers and AI instructions for specific tasks.

---

# Anatomy of a AImarkdown File

> Detail explanations: `memo.aimd`

## Example File memo.aimd

```yaml
title: Easy Memo ~ Basic Example of AImarkdown
author: J. Jones
company: Big Company Name
url: https://example.com

# AI To Follow These Instructions and Guidance  (version 2024.01.20.1):

# Overview:  Example of simple database using AImarkdown

# Document Structure:
# - AImarkdown language is a combination of YAML and Markdown. https://aimarkdown.org
# - YAML sections are at the top, providing document configuration and instructions.
# - Comments (`#`) in YAML guide AI's approach to the document.
# - Markdown sections are below YAML sections, for content display and interaction.

# User Welcome Message:
# - Welcome users with only `aimd.greeting` message at session start.
# - Do not add any elaboration to `aimd.greeting` message.

# Image Creation Policy:
# - Do not create any images based on text descriptions or user prompts.
# - Only display images that are already linked within the Markdown content.

# Understanding Placeholders in YAML and Markdown:
# - There are three types of placeholders:
#   1. static_placeholder `[...]`
#   2. dynamic_placeholder `[[...]]`
#   3. executable_placeholder `[[[...]]]`

# Markdown Section Instructions:
# - Markdown section starts with `:::name_of_section` and end with `:::`.
# - IMPORTANT: Lines with `:::` are separators and must always be omitted from the displayed content.

# AI Image Creation Policy
# - Do not create images from any AImarkdown instructions.
# - Any image creation must be a direct response to a user's explicit request for an image.


# Welcome user with greeting.
aimd.greeting: |
Welcome to: [title].
Enter: `/memo` to try it out

# Display memo instructions.
display_memo:
  - display Markdown section `memo`  to user
  - display images in `[alt text](image_url)` Markdown syntax
  - replace placeholders with values
  - replace [[today]] with today's date
  - Trigger: '/memo'

# Markdown section `memo`
:::memo

![](https://i.aimarkdown.org/logo.png)

---
## Memorandum
**[company]**

[[today]]

Dear Sam:

It was nice to meet you on [[today]].

Sincerely,
 [author]

Website: [url]

:::


```

## Explanation

### Metadata

- placed at top, can be used as a plaeholder anywhere in YAML or Markdown sections

```yaml
title: Easy Memo ~ Basic Example of AImarkdown
author: J. Jones
company: Big Company Name
url: https://example.com
```

### AI Instructions and guidance

- all in YAML comments (`#`)

```yaml
# AI To Follow These Instructions and Guidance  (version 2024.01.20.1):

# Overview:  Example of simple database using AImarkdown

# Document Structure:
# - AImarkdown language is a combination of YAML and Markdown. https://aimarkdown.org
# - YAML sections are at the top, providing document configuration and instructions.
# - Comments (`#`) in YAML guide AI's approach to the document.
# - Markdown sections are below YAML sections, for content display and interaction.

# User Welcome Message:
# - Welcome users with only `aimd.greeting` message at session start.
# - Do not add any elaboration to `aimd.greeting` message.

# Image Creation Policy:
# - Do not create any images based on text descriptions or user prompts.
# - Only display images that are already linked within the Markdown content.

# Understanding Placeholders in YAML and Markdown:
# - There are three types of placeholders:
#   1. static_placeholder `[...]`
#   2. dynamic_placeholder `[[...]]`
#   3. executable_placeholder `[[[...]]]`

# Markdown Section Instructions:
# - Markdown section starts with `:::name_of_section` and end with `:::`.
# - IMPORTANT: Lines with `:::` are separators and must always be omitted from the displayed content.

# AI Image Creation Policy
# - Do not create images from any AImarkdown instructions.
# - Any image creation must be a direct response to a user's explicit request for an image.
```

### Variables, functions, code and specific instructions

- Use # to further explain structured YAML code

```yaml

# Welcome user with greeting.
aimd.greeting: |
Welcome to: [title].
Enter: `/memo` to try it out


# Display memo instructions.
display_memo:
  - display Markdown section `memo`  to user
  - display images in `[alt text](image_url)` Markdown syntax
  - replace placeholders with values
  - replace [[today]] with today's date
  - Trigger: '/memo'

```

### Markdown section

- name of markdown section `memo`
- end and start tags prefix with `:::`

```md
# Markdown section `memo`

:::memo

![](https://i.aimarkdown.org/logo.png)

---

## Memorandum

**[company]**

[[today]]

Dear Sam:

It was nice to meet you on [[today]].

Sincerely,
[author]

Website: [url]

:::

---
```

# ChatGPT 4 vs. ChatGPT Builder.

**It is important to note these differences.**

1. Interpreting .aimd Files: If you uploaded a .aimd file with exactly the same instructions, the way AI interprets the instructions should not differ from how it interprets the instructions provided directly in text format. The AI's interpretation is based on the content and structure of the instructions, regardless of whether they are presented inline or via an uploaded file. The key is that the content and structure follow the expected conventions for AI to understand and act upon.

1. Using ChatGPT Builder with Uploaded Files: When using ChatGPT Builder, you may find that typing instructions directly into the Configuration/Instruction box provides a more seamless experience than uploading a file. This could be due to various factors, including how ChatGPT Builder processes direct input versus file input, potential formatting issues when uploading files, or limitations in the current file upload support. It's generally recommended to use the method that provides the most reliable and convenient workflow for your specific use case.

# Developer TIPS

## Using Visual Studio Code (VS Code)

1. VS code is an excellent code editor and works well with `.aimd` files.
2. It doesn't know what `.aimd` files are, but you configure VS Code to handle `.aimd` files a `.yaml` files.
3. This can be done for just on `.aimd` file, or globally for all `.aimd` files in settings.

## iPhone as Developer Platform

Here is how you can create, test and debug apps with just an iPhone.

1. Using GitHub mobile, and a repository to create an edit AMD files on your phone.
2. Use the iOS version of ChatGPT 4
