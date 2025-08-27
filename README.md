# Context Networks

A collaborative framework for human-AI knowledge management focused on relationships between information rather than just storage. Includes guides and templates for creating evolving knowledge systems with AI partners.

## 📚 Documentation

For comprehensive documentation, guides, and explanations, visit our GitHub Pages site:

**[Context Networks Documentation](https://jwynia.github.io/context-networks/)**

## 🗂️ Repository Structure

```
├── .claude/                   # Claude Code custom commands and configurations
│   └── commands/              # Context network workflow commands (see below)
├── agent-specific-prompts/    # Specialized prompts for different AI assistants
│   ├── claude-code/           # Prompts optimized for Claude Code
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
3. For Claude Code users: Explore the [custom commands](.claude/commands/) designed for context network workflows

### Initializing a Context Network
Here's a practical step-by-step process for starting a new context network:

1. **Create a project structure**
   - Create an empty folder or git repository for your project
   - Add an "inbox" folder for temporary document storage
   - Place a copy of /core/comprehensive-context-network-guide.md in the inbox folder.

2. **Initialize the context network**
   - Use an AI assistant like Claude Code, Cline (in Plan mode), or another agentic tool with a prompt similar to:
     ```
     In the inbox folder is a guide to context networks. I want to create a context network folder and .context-network.md entry point for a [type of] project. I will be providing additional documents from outside this project for integration into the context network after it is set up. They will always be dropped into the inbox folder. They should always be completely processed and integrated into the context network and then archived, leaving the inbox empty after integration.
     ```
   - Provide a paragraph describing the goal of your project
   - If using Cline: Review the AI's plan and switch to Act mode to set up the structure
   - If using Claude Code or other tools: Review the proposed approach before proceeding

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

### Working with Claude Code

Claude Code includes specialized commands for context network workflows. Key commands include:

- **Planning & Research**: `/plan`, `/research` - Design and investigate without implementation
- **Implementation**: `/implement`, `/refactor` - Turn plans into working solutions
- **Quality**: `/audit`, `/review-tests` - Ensure quality and security
- **Task Management**: `/groom`, `/status` - Organize and track progress
- **Maintenance**: `/sync`, `/maintenance`, `/retrospective` - Keep everything up-to-date
- **Documentation**: `/discovery`, `/checklist` - Capture knowledge systematically

Common workflow sequences:
1. **Daily**: `/sync` → `/status` → `/groom`
2. **Weekly Planning**: `/sync` → `/retrospective` → `/groom` → `/plan`
3. **Quality Check**: `/audit` → `/review-tests` → `/refactor`

See the [Claude commands documentation](.claude/commands/README.md) for detailed usage and creating custom commands.

## 🚀 Version 2.0 Development: Universal Context Engine

We're actively developing the next evolution of context networks - the **Universal Context Engine**. This represents a fundamental shift from manual markdown-based networks to an intelligent, automated system that addresses the core limitations we've observed in real-world usage.

### What's Coming in V2

The Universal Context Engine will provide:

- **Automated Context Management**: Eliminate the manual maintenance burden that causes context networks to degrade over time
- **Multi-Perspective Access**: Same information accessible from multiple organizational views (think "index" vs "table of contents")
- **Intelligent Deduplication**: Prevent the "amnesia loop" where agents create duplicate files like `current_tasks.md`, `todo.md`, `next_steps.md`
- **Historical Context Preservation**: Full project evolution history, including deleted branches and failed experiments
- **Cross-Domain Pattern Recognition**: Universal patterns that work across code, documents, contracts, and other domains
- **Decision Governance Integration**: Collaborative decision-making system to prevent agents from making unilateral architectural choices

### Key Technical Innovations

- **Dual Database Architecture**: Kuzu (graph) + DuckDB (analytics) for optimal relationship storage and querying
- **Progressive Memory Model**: Working memory → semantic storage → episodic archive (inspired by human memory)
- **Lens System**: Context automatically adapts based on your current task (debugging, feature development, refactoring, etc.)
- **Continuity Cortex**: Intelligent layer that intercepts file operations to prevent duplication and maintain consistency

### 📋 We Need Your Feedback!

If you've used context networks in real projects, your experience is invaluable for V2 development. We're especially interested in:

**Your Pain Points:**
- What maintenance burden did you experience?
- Where did agents struggle with the current system?
- What information got duplicated or went stale?
- When did you abandon or scale back your context network?

**Your Success Stories:**
- What worked really well?
- Which patterns should we preserve?
- What made the biggest difference to your productivity?
- How did context networks change your workflow?

**V2 Feedback:**
- Which proposed features excite you most?
- What concerns do you have about automated systems?
- How do you envision using the decision governance system?
- What domains (beyond code) would you want to try this with?

### 📖 Read the Full V2 Proposals

- **[Universal Context Engine - Technical Design](proposals/context-network-engine-v2.md)**: Complete 5-document set covering problem analysis, architecture, implementation guide, and API reference
- **[Decision Approval System](proposals/agent-decision-making.md)**: Protocol for collaborative human-AI decision making

### 💬 How to Share Feedback

- **GitHub Discussions**: [Start a discussion](../../discussions) about your experience or questions
- **Issues**: [Open an issue](../../issues) for specific bugs, feature requests, or problems you've encountered
- **Email**: Direct feedback to [your-email] for detailed case studies or sensitive information

Your real-world experience is what will make V2 truly useful. Even "failed" experiments or partial implementations provide valuable insights!

## FAQ
- Why isn't the context network working well out of the box?
  - Because a newly-initialized context network is basically just the structure/rules/explanation of the way of working, it takes some interactions and things being added for a context network to settle in. 
- Why isn't this project itself managed by a context network?
  - Excellent question, fellow "meta" enthusiast. My own default instinct is to want to go similarly meta on pretty much everything I touch. I've tried using context networks to make context networks, to manage information about them, etc. At the moment, everything I've tried to make that work has left the agents I've used (with every model I've tried) confused. If someone can get it to keep the concepts separate in the process, I'd love the contribution. And, I'll definitely continue trying myself when new models come out. Until then, I often use a Claude project with specific files from this project to work on how to improve it and use manual tracking of things and "regular" agentic assistance.
- Will V2 replace the current markdown-based approach?
  - Not immediately. V2 is designed to run alongside existing context networks initially, with a gradual migration path. The markdown approach will remain as a backup and for users who prefer manual control.

## 🤝 Contributing

Contributions are welcome! Please check out our [contribution guidelines](CONTRIBUTING.md) for details on how to get started.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Inspired by [Cline's Memory Bank](https://docs.cline.bot/improving-your-prompting-skills/cline-memory-bank) and other memory systems for LLMs
- Developed through collaborative iterations with Claude, Claude Code, and other AI assistants
- Thanks to all contributors and early adopters who have helped refine this framework
