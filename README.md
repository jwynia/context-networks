# Context Networks

A collaborative framework for human-AI knowledge management focused on relationships between information rather than just storage. Includes guides and templates for creating evolving knowledge systems with AI partners.

## 📚 Documentation

For comprehensive documentation, guides, and explanations, visit our GitHub Pages site:

**[Context Networks Documentation](https://jwynia.github.io/context-networks/)**

## 🗂️ Repository Structure

```
├── agent-specific-prompts/    # Specialized prompts for different AI assistants
│   ├── cline/                 # Prompts optimized for Cline
│   └── roo/                   # Prompts optimized for Roo
├── core/                      # Core framework concepts and documentation
├── docs/                      # Documentation site source files
├── example-networks/          # Sample context networks for different use cases
├── prompts/                   # General-purpose prompt templates
│   └── simple/                # Simplified prompt templates for getting started
├── tools/                     # Utilities and scripts
│   └── generators/            # Tools for generating context network components
├── CONTRIBUTING.md            # Contribution guidelines
├── LICENSE                    # MIT License
└── README.md                  # This file
```

## 🚀 Getting Started

### Understanding Context Networks
1. Visit the [documentation site](https://jwynia.github.io/context-networks/) to understand the framework concepts
2. Review the [Comprehensive Guide](core/comprehensive-context-network-guide.md) for detailed information

### Initializing a Context Network
Here's a practical step-by-step process for starting a new context network:

1. **Create a project structure**
   - Create an empty folder or git repository for your project
   - Add an "inbox" folder for temporary document storage
   - Place a copy of /core/comprehensive-context-network-guide.md in the inbox folder.

2. **Initialize the context network**
   - Use an AI assistant like Cline in Plan mode with a prompt similar to:
     ```
     In the inbox folder is a guide to context networks. I want to create a context network folder and .context-network.md entry point for a [type of] project. I will be providing additional documents from outside this project for integration into the context network after it is set up. They will always be dropped into the inbox folder. They should always be completely processed and integrated into the context network and then archived, leaving the inbox empty after integration.
     ```
   - Provide a paragraph describing the goal of your project
   - Review the AI's plan and switch to Act mode to set up the structure

3. **Commit your context network**
   - Version control is critical for context networks
   - Commit changes frequently as you build out your network

4. **Optimize for your project**
   - Follow up with: "Is there anything about the current design of the context network that should change to better suit the project goals? Better ways of linking information for dense and rapid navigation?"
   - Consider adding specialized agent prompts to the project folder
   - Brainstorm with AI assistants about additional modes that might make sense for your project

5. **Integrate external documents**
   - Drop documents into the inbox folder
   - Work with AI assistants to process and integrate them into the context network
   - Archive processed documents to keep the inbox empty

For more detailed examples, check the [example-networks](example-networks/) directory.

## FAQ
- Why isn't the context network working well out of the box?
  - Because a newly-initialized context network is basically just the structure/rules/explanation of the way of working, it takes some interactions and things being added for a context network to settle in. 
- Why isn't this project itself managed by a context network?
  - Excellent question, fellow "meta" enthusiast. My own default instinct is to want to go similarly meta on pretty much everything I touch. I've tried using context networks to make context networks, to manage information about them, etc. At the moment, everything I've tried to make that work has left the agents I've used (with every model I've tried) confused. If someone can get it to keep the concepts separate in the process, I'd love the contribution. And, I'll definitely continue trying myself when new models come out. Until then, I often use a Claude project with specific files from this project to work on how to improve it and use manual tracking of things and "regular" agentic assistance.

## 🤝 Contributing

Contributions are welcome! Please check out our [contribution guidelines](CONTRIBUTING.md) for details on how to get started.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Inspired by [Cline's Memory Bank](https://docs.cline.bot/improving-your-prompting-skills/cline-memory-bank) and other memory systems for LLMs
- Developed through collaborative iterations with Claude and other AI assistants
- Thanks to all contributors and early adopters who have helped refine this framework
