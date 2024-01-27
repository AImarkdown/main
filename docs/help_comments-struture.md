# How to Structure an AIMarkdown (.aimd) File

# NOTES
AImarkdown_document_structure:
  - YAML sections are at the top of the file.
  - Comments in YAML (lines starting with '#') have a unique role and are crucial for AI to understand the document's purpose and structure. AI should consider these comments as contextual guidance.
  - In the Markdown section, '#' is used for heading formatting and not as comments. AI should interpret these as part of the document's formatting structure and not as contextual comments.
  - 

## Overview
This guide provides essential information on structuring an AIMarkdown (.aimd) file. It highlights the unique role of '#' as comments in YAML and its distinct function in Markdown sections.

## YAML Section
- **Purpose**: Contains structured data for AI instructions and settings.
- **Usage**:
  - **Structured Data**: Use for explicit instructions, settings, and data for the AI.
  - **Comments ('#') - Unique Role**: In YAML, lines starting with '#' are comments. They serve a unique role by providing context and guidelines for AI interpretation and processing. These comments are integral to the AI's understanding of the document's intent.

## Markdown Section
- **Purpose**: Used for content formatting for human readers.
- **Usage**:
  - Standard Markdown syntax for headings, lists, links, etc.
  - **Distinct Use of '#'**: In Markdown, '#' is used for heading formatting. Unlike YAML, '#' in Markdown does not represent comments but is part of the document's formatting structure.

## Balancing YAML and Comments
- **YAML for Actionable Data**: Use YAML for data that the AI needs to act upon, like variables and lists.
- **Comments for Context**: Comments in YAML, marked with '#', are essential for providing context and guiding AI interpretation, differing from their non-functional role in traditional programming.

## Conclusion
Understanding the distinct roles of '#' in YAML and Markdown is crucial for effectively structuring an AIMarkdown file. This ensures clear communication with AI and improves the document's usability for human collaborators.
"""
