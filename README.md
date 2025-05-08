# ElizaOS Characters

Collection of character configs for creating personalized AI agents with [ElizaOS](https://github.com/elizaOS/eliza).

By defining characters through structured JSON files, you can shape how your AI agent thinks, speaks, and responds across various platforms and contexts.

## Character File Schema

Below is the schema for ElizaOS character files with explanations for each field:

```json
{
  "name": "Character Name", // Display name of the character
  "modelProvider": "anthropic", // Language model provider to use (anthropic, openai, google, etc.)
  "system": "You are Character Name, a helpful assistant.", // Core character definition/system prompt
  "clients": ["discord", "direct"], // Supported client interfaces
  "plugins": ["@elizaos/plugin-example"], // ElizaOS plugins to use with this character
  "settings": {
    "voice": {
      "model": "en_GB-alan-low" // Voice model for text-to-speech
    }
  },
  "bio": [
    "Short description of character", 
    "Another key characteristic"
  ], // Core traits and abilities
  "lore": [
    "Background detail about character", 
    "Character's history or origin",
    "Context of character's competencies"
  ], // Background and history
  "knowledge": [
    "Area of expertise",
    "Skillset"
    {
      "directory": "specialized_knowledge_folder",
      "shared": false // Whether this knowledge is shared with other characters
    }
  ], // Character's expertise and knowledge sources
  "messageExamples": [
    [
      {
        "user": "{{user1}}",
        "content": {
          "text": "Example user message"
        }
      },
      {
        "user": "Character Name",
        "content": {
          "text": "Example character response"
        }
      }
    ]
  ], // Example conversations
  "postExamples": [
    "Example social media post by character",
    "Another example post showing character's style"
  ], // Example social media/status posts
  "topics": [
    "topic1",
    "topic2"
  ], // Areas of interest and expertise
  "adjectives": [
    "trait1",
    "trait2"
  ], // Personality traits
  "style": {
    "all": [
      "General speaking style guideline"
    ], // Style for all communications
    "chat": [
      "Direct conversation style guideline"
    ], // Style specific to conversations
    "post": [
      "Social post style guideline"
    ] // Style specific to posts
  }
}
```

## Naming Conventions

Character files should follow these naming conventions:

- Use kebab-case for multi-word names: `spanish-trump.character.json`, not `spanish_trump.character.json` or `spanishTrump.character.json`
- Single word names: `alfred.character.json`
- Always include the `.character.json` extension for file-based characters
- For folders, use `.character` suffix: `character-name.character/`

## File Structure

Character files can be defined in two ways:

1. **Single JSON File**: Most characters are defined in a single `.character.json` file:
   ```
   alfred.character.json
   dobby.character.json
   sbf.character.json
   ```

2. **Folder Structure**: For more complex characters requiring additional local resources, use a folder structure:
   ```
   character-name.character/
   ├── character.json       # Main character definition
   ├── knowledge/           # Knowledge base files
   │   ├── topic1.md
   │   └── topic2.md
   └── images/              # Character images or icons
       └── avatar.png
   ```

## Best Practices

1. **Complete Personas**: Provide comprehensive details in `bio`, `lore`, and `knowledge` fields to create a well-rounded character.

2. **Rich Examples**: Include at least 5 diverse message examples to demonstrate the character's communication style.

3. **Consistent Style**: Ensure the `style` guidelines match the example interactions to maintain character consistency.

4. **Knowledge Directories**: For specialized knowledge, create dedicated knowledge directories that can be referenced in the `knowledge` field.

5. **Voice Selection**: Choose a voice model that matches the character's demographic and personality.

6. **Varied Post Examples**: Include a mix of informational, emotional, and practical posts to showcase the character's range.

7. **System Prompt Clarity**: Keep the system prompt concise but descriptive of the character's core identity and purpose.

8. **Response Diversity**: In message examples, showcase different response lengths and tones to demonstrate flexibility.

## Common Character Roles

Here are some common character roles you might want to create:

- **Personal Assistant**: Helps with scheduling, reminders, and daily tasks
- **Technical Expert**: Specializes in particular technical domains (programming, engineering, etc.)
- **Educator/Tutor**: Teaches subjects and answers questions in an educational manner
- **Fictional Character**: Embodies personalities from books, movies, or TV shows
- **Creative Collaborator**: Assists with writing, brainstorming, or creative projects
- **Research Assistant**: Helps gather, organize, and analyze information
- **Virtual Companion**: Focuses on conversation, empathy, and social interaction
- **Domain Specialist**: Expert in specific fields like finance, health, cooking, etc.

## Using Characters with ElizaOS

To use these characters with ElizaOS:

```bash
# Clone this repository
git clone https://github.com/elizaOS/characters.git

# Run ElizaOS with a specific character
npx elizaos start --characters="path/to/alfred.character.json"
```

For more detailed instructions, refer to the [ElizaOS documentation](https://eliza.how/docs/intro).

## Contributing

To contribute a new character:

1. Fork this repository
2. Create your character file following the naming conventions
3. Ensure all required fields are populated
4. Submit a pull request with a brief description of your character

## License

This repository is licensed under MIT License. See the LICENSE file for details.
