# Mintlify Documentation Style Guide

This guide establishes standards for using Mintlify features to create consistent, engaging, and user-friendly documentation.

## Core Principles

1. **Clarity First**: Content should be clear and concise before it's visually enhanced
2. **Progressive Disclosure**: Layer information from basic to advanced
3. **Visual Consistency**: Use components consistently to build reader familiarity
4. **Scannable Content**: Structure content for both deep reading and quick scanning
5. **Mobile Optimization**: Ensure all components work well on smaller screens

## Component Usage Guidelines

### Page Structure

#### Front Matter
- **Required Fields**: Always include `title` and `description`
- **Description Format**: Keep descriptions between 100-160 characters and focus on user benefits
- **Example**:
  ```mdx
  ---
  title: "Feature Name"
  description: "Concise explanation of what this feature does and its primary benefit to the user."
  ---
  ```

#### Page Introduction
- Begin each page with a clear, concise paragraph that sets context
- Avoid redundancy with the page description
- Aim for 2-3 sentences that explain the "why" of the feature

### Headers and Hierarchy

- Use proper header hierarchy (H1 → H2 → H3)
- Avoid skipping levels (don't jump from H2 to H4)
- Keep headers concise (3-7 words)
- Use sentence case for consistency

### Cards and Layouts

#### `<Card>` Component
- **Best For**: Navigation, feature highlights, condensed information
- **Icon Usage**: Always include relevant icons to improve scannability
- **Title Length**: Keep titles under 5 words
- **Content Length**: Card content should be concise (1-3 sentences)
- **Linking**: Use the `href` attribute for navigation cards

#### `<Columns>` Component
- **Best For**: Side-by-side comparisons, feature lists, balanced layouts
- **Column Count**: Use `cols={2}` for most content, `cols={3}` for simpler items
- **Mobile Behavior**: Content stacks on mobile, so ensure each column makes sense in isolation
- **Example**:
  ```mdx
  <Columns cols={2}>
    <Card title="First Feature" icon="star">
      Concise description.
    </Card>
    <Card title="Second Feature" icon="rocket">
      Concise description.
    </Card>
  </Columns>
  ```

### Information Disclosure

#### `<Accordion>` Component
- **Best For**: Progressive disclosure, FAQs, examples, detailed explanations
- **Title Format**: Use descriptive titles that indicate content (avoid "More Info")
- **Icon Usage**: Optional but helpful for quick identification
- **Content Scope**: Each accordion should address a single concept

#### `<AccordionGroup>` Component
- **Best For**: Grouping related accordions, step-by-step guides, categorized information
- **Nesting**: Limit nesting to 2 levels deep for readability
- **Example**:
  ```mdx
  <AccordionGroup>
    <Accordion title="First Step">Content</Accordion>
    <Accordion title="Second Step">Content</Accordion>
  </AccordionGroup>
  ```

### Tables

- **Left-Align Text**: Always use `|:-----|` format for better readability
- **Header Row**: Use bold formatting for header row
- **Column Width**: Keep tables to 3-4 columns maximum for mobile readability
- **Row Count**: Aim for 10 or fewer rows; consider alternative formats for longer data sets
- **Example**:
  ```mdx
  | Feature | Status | Description |
  |:--------|:-------|:------------|
  | Item 1  | ✅     | Description |
  ```

### Code Blocks

- **Language Specification**: Always specify the language for syntax highlighting
- **Line Highlighting**: Use line highlighting for important sections
- **Captions**: Add captions to complex code examples
- **Example**:
  ```mdx
  ```js {3-5} "Caption: Key implementation"
  function example() {
    // Regular code
    // Highlighted important code
    // Highlighted important code
    // Highlighted important code
    // Regular code
  }
  ```
  ```

### Images and Media

- **Alt Text**: Always include descriptive alt text
- **Captions**: Add captions to clarify complex visuals
- **Size**: Optimize images for web (< 200KB when possible)
- **Borders**: Use borders for screenshots that might blend with the page
- **Example**:
  ```mdx
  ![Alt text describing the image](../images/example.png)
  ```

## Content Patterns

### Use Case Presentation

- **Structure**: Problem → Solution → Example
- **Components**: Use Cards in Columns for multiple use cases
- **Icons**: Use consistent icons for similar use cases

### Step-by-Step Guides

- **Structure**: Each step in separate Accordion within AccordionGroup
- **Numbering**: Use explicit numbering in titles ("Step 1:", "Step 2:")
- **Code Examples**: Include relevant code for implementation steps

### Comparison Tables

- Use tables for feature/option comparisons
- Include "Best For" column to guide selection
- Left-align all text for readability

### API Documentation

- Use consistent structure: Description → Parameters → Returns → Examples
- Code examples should be complete and functional
- Include both success and error handling examples

## Mobile Optimization

- Test layouts on mobile views
- Avoid more than 3 columns on any layout
- Keep table columns minimal (3-4 max)
- Ensure code blocks have horizontal scrolling on mobile

## Common Patterns to Avoid

1. **Overusing Accordions**: Don't hide critical information
2. **Inconsistent Icons**: Stick to a single icon library
3. **Deep Nesting**: Limit component nesting to 2-3 levels
4. **Wall of Text**: Break up long paragraphs with subheadings or lists
5. **Orphaned Information**: Ensure all content has proper hierarchy and context

