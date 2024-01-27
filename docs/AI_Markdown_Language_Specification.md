
# AImarkdown Language Specification
> v. 1.0  Dec 23, 2023 : 9:43 AM


## Overview
AImarkdown (AIMD) is a specialized Markdown language combining *Markdown* and *YAML* languages. It is designed to facilitate AI interactions and create AI-powered applications. 

It extends traditional Markdown with AI-specific constructs.

**IMPORTANT**
- AI can often overlook error and typos, but you are far better to make your `.aimd` files as error-free and clear as possible.



## Suggested Style Guide

### YAML Section Use of Comments

**YAML** section
- comments are `#` and should occur on their own line starting with `#`
- Example

```yaml
# this is a comment
```

### Indents
- are two spaces and in the YAML section
- as a matter of fact, traditional YAML demands this


### Line spacing
- Separate parts of YAML with single line
- Separate Markdown sections with a double line
- 
- Meta data should occur at top of document 

- Examples

Meta data:
 ```YAML
author: Joe Smith
```

### Variables:
- variables show be long enough to express meaning
- spaces are `_`
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

 ### Multiple AIMD sections, can be used , use terminater `...`
 - rob improve on this eith example
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

### Triggers
- refer to user prompts.
- Specific commands or phrases that activate certain AI functions.
- Specified in the YAML section under `AI_Instructions`.
- Example: `Trigger: /bm` activates the bookmark function.

## Usage Examples

### Bookmarking
- Use `:::bookmark` to define a bookmark template.
- Example:
  ```md
  :::bookmark
  🔴 BM: **[[bookmark_number]]** → *[[today]]*
  *Note*: [bookmark_note]
  :::
  ```

### Help Section
- Use `:::bookmark_help` for a help template.
- Example:
  ```md
  :::bookmark_help
  ### ❓Help
  > **ChatMarker** bookmarks chat messages.
  ...
  :::
  ```

## Extensions and Customization
- AIMD can be extended with custom tags and placeholders.
- Users can define their own triggers and AI instructions for specific tasks.

## Conclusion
AImarkdown is a versatile tool designed to enhance and streamline AI-powered applications and interactions. Its combination of YAML and Markdown provides a structured yet flexible way to create interactive AI content.
