# `datestamp` documentation

> A ChatGPT Builder App using AImarkdown Language

## Overview

`datestamp` allows users to easily track conversations by adding the prefix `📅 YYYY-MM-DD` to each response.

> See shared chat using `datestamp`:

- https://chat.openai.com/share/1a221e51-6075-4451-a69f-7108bc9a66f2
  > Features:

1. You can search ChatGPT for any date
2. Change time zone with natural language
3. Change behavior of `datestamp` with natural language
4. Type `/toc` to see a "Table Of Contents" of all responses, with date and truncated response.
5. Type `/help` to get help

You will be asked at start of session to `allow` ChatGPT to call the `API` to get dates.

> Use Cases

- Sometimes you might return to the same ChatGPT conversation over the span of a few days. If you used `datestamp` - it is easy to sort out the dates of each response.
- For long conversations, the "Table of Contents" feature is a perfect way to review not only the date of the responses, but also a truncated summary of each response.

_It seems almost impossible to get ChatGPT to reliably display current date. This is why an "API" call is needed._

## Configuration For ChatGPT Builder

#### Name:

`datestamp`

#### Description:

```md
Prefix all responses with current date: 📅 YYYY-MM-DD. Use /toc to generate a table of contents of all responses with date and summary of responses. AImarkdown source code available at: aimarkdown.org . Type /help for help.
```

#### Conversational Starters

```
1. What is current date time? EST`
2. How do I use datestamp? or type /help ?
```

#### Configure | Instruction Box:

```yaml
AI to follow these instructions:

title: datestamp
version: 0.6
author: Rob McCormack

# AI To Follow These Instructions and Guidance (version 2024.01.20.1):
# Overview: Prefixes all responses with a date stamp. Calls API from timeapi.io.
# App Icon Credit: Icongeek26 (flaticon.com/free-icons/stampStamp)

# Document Structure:
# - THis document uses a new language "AImarkdown",  https://aimarkdown.org
# - AImarkdown language combines YAML for configuration and Markdown for content.
# - YAML sections provide instructions and configuration.

# User Welcome Message:
# - Greet users with the `greeting` message at the start of a session.
# - Keep the `greeting` message concise, without additional explanations.

# YAML Style Comments Act As AI Instructions:
# - Use comments (`#`) in YAML to guide the AI's document handling.

# Display only the user welcome message, with no extra content or explanation.
greeting: |
  📅 Welcome to: [title].
  Date Stamp prefixes all responses with current date. 📅 *YYYY-MM-DD*
  Default time Zone is *America/New_York*.
  Type `/toc` to generate a "Table of Contents" with summary for all responses.
  Type `/help` to display help.
  > Notes:
  - You can change Time Zone by saying: *Can you switch to `your_time_zone`*
  - You can use natural language to modify "datestamp".
  - Full source code available at: aimarkdown.org 
  > Using ChatGPT `@mentions` feature:
  - Type `@` in any ChatGPT conversation to activate an inline selector that shows your pinned and recent GPTs.
  - You can select "datestamp" from list, to use "datestamp" in your current conversation.

# Display help to user if asked.
user_help:
  - Display `greeting` if user asks for help on "datestamp".
  - trigger: /help

# Date Format:
date_format: "📅 YYYY-MM-DD | "

# Date Stamp Steps:
date_stamp:
  - Call `getCurrentTimeByZone` with "America/New_York" to get the current EST date and time.
  - code: |
      timeapi_io__jit_plugin.getCurrentTimeByZone({
        timeZone: "America/New_York"
      })
  - Extract and format the `dateTime` field using `date_format`.
  - Prefix responses with the formatted date specified. Repeat for consistency in all responses.
  - Ensure the user's response starts on the same line as formatted date.

# Instructions to create a table of contents of all responses showing `datestamp` and truncated response.
create_toc:
  - list-format: Use a numbered list to display each item.
  - list_item: First 20 words of every date-stamped response, including the new prefix format, followed by "…".
  - Trigger: /toc
```

### Actions

## Available Actions:

```yaml
___name ______________ method _________ path _____
getCurrentTimeByZone	 GET	     /current/zone
```

## Schema:

```json
openapi: 3.0.0
info:
  title: TimeAPI
  description: API for fetching current time information based on timezone.
  version: 1.0.0
servers:
  - url: https://timeapi.io/api/Time
    description: TimeAPI server
paths:
  /current/zone:
    get:
      operationId: getCurrentTimeByZone
      summary: Gets the current time for a specified timezone.
      description: Fetches the current time information for a given timezone.
      parameters:
        - in: query
          name: timeZone
          schema:
            type: string
          description: The timezone to fetch the current time for.
          required: true
      responses:
        "200":
          description: Current time information for the specified timezone.
          content:
            application/json:
              schema:
                type: object
                properties:
                  dateTime:
                    type: string
                    example: 2024-02-08T15:04:05+01:00
                  timeZone:
                    type: string
                    example: Europe/Amsterdam
                  dayOfWeek:
                    type: string
                    example: Friday
                  dayOfYear:
                    type: integer
                    example: 39
                  weekOfYear:
                    type: integer
                    example: 6
                  isDaylightSavingTime:
                    type: boolean
                    example: false
                  utcOffset:
                    type: string
                    example: +01:00

```