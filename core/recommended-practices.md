# Recommended Practices for Context Networks

This document outlines key recommended practices for effectively creating, managing, and utilizing context networks, particularly for human users.

## File Size Management and Hierarchical Organization

As context networks grow, individual files can become unwieldy, making navigation and maintenance difficult. Implementing hierarchical organization patterns helps maintain usability and scalability.

### When to Apply Hierarchical Organization

Consider implementing hierarchical organization when:

1. **File Size**: Individual files exceed 1000 lines or 50KB
2. **Content Growth**: Information is regularly added and will continue to grow over time
3. **Navigation Challenges**: Finding specific information within a file becomes difficult
4. **Multiple Categories**: Content naturally falls into distinct categories or types
5. **Reference Frequency**: Information is frequently referenced and needs to be easily accessible
6. **Collaboration**: Multiple contributors need to work with the content simultaneously

### Core Hierarchical Pattern

```
content_type/
├── index.md                    # Main entry point with navigation and recent entries
├── category_a/                 # First major category
│   ├── index.md                # Category-specific index
│   ├── subcategory_1/          # Optional subcategories for deeper organization
│   │   ├── index.md            # Subcategory index
│   │   ├── item_1.md           # Individual content items
│   │   └── item_2.md
│   ├── item_a.md               # Category-specific items
│   └── item_b.md
├── category_b/                 # Second major category
│   ├── index.md
│   └── [content items]
└── templates/                  # Templates for consistent content creation
    └── item_template.md
```

### Implementation Steps

1. **Content Analysis**: Identify natural categories and logical hierarchies
2. **Directory Structure Design**: Create a structure that reflects natural categories and allows for future expansion
3. **Index File Creation**: Create index files at each level that provide overview, purpose, and navigation
4. **Content Migration**: Move content from monolithic files to the new structure, maintaining consistency
5. **Reference System Implementation**: Ensure robust linking between related content
6. **Template Creation**: Create templates for new content to maintain consistency

### Example: Updates Tracking System

A common use case is breaking down a large `updates.md` or `update_log.md` file:

```
updates/
├── index.md                    # Main entry point with recent updates across all categories
├── infrastructure/             # Infrastructure-related updates
│   ├── index.md                # Index of all infrastructure updates
│   └── [individual updates]
├── research/                   # Research-related updates
│   ├── index.md                # Index of all research updates
│   └── [individual updates]
└── templates/                  # Templates for consistent update creation
    └── update_template.md
```

### Migration Strategy

When migrating from a monolithic file:

1. Create the structure first with index files
2. Add a deprecation notice to the original file with a link to the new structure
3. Migrate incrementally, category by category
4. Update references to the original file
5. Maintain both temporarily until migration is complete
6. Document the process for future reference

### Design Principles

- **Depth vs. Breadth**: Aim for a maximum of 3 hierarchy levels; prefer more categories at the same level over deeper nesting
- **Naming Conventions**: Use consistent, descriptive naming patterns
- **Cross-Cutting Concerns**: Use the main index to highlight cross-cutting content and implement tagging

## Code Projects

### Packages and Framework Reference Material
When using packages and frameworks, one of the easiest ways to give it info to ground in current documentation instead of hallucinating or instead of trying to coax agents into using MCP servers or tools is to clone the repo of the project that holds the package/framework/docs for the thing you're using into some place like /reference/some-npm-repo or similar. 

You can remove the .git folder and add it to .gitignore, but note that many of the VSCode-based agent tools won't look at files ignored in the .gitignore, as well as files like .env (there are good reasons for it, but it can also get in the way of what you intend). Note that this is also often why folders like node_modules won't be used to answer questions about API definitions for method signatures, etc.

You can also treat that reference repo as a submodule. 

I'm not a fan of letting the agents read files outside the project,but that could work too.

Once you've added it, prompt with something like:
```
I just added a copy of the A2A specification repository in /reference/a2a. Update the context network with that resource being available and use it for any questions about the A2A specification.
```


### Version Control Best Practices

Effective management of a context network, especially in collaborative or AI-assisted environments, relies heavily on disciplined version control:

*   **Commit Frequently:** Treat the context network like critical code. Commit changes very often, ideally after each significant update or refinement to a node or relationship. This creates a detailed history and minimizes potential data loss. Small, atomic commits make it easier to understand changes and revert if necessary.
*   **Branch Aggressively:** Don't hesitate to use branches for exploring new structures, drafting significant changes, or isolating work on specific sections of the network (e.g., planning a new feature). Short-lived branches are generally preferred.
*   **Merge Challenges:** Be aware that merging branches that modify the `context-network` directory structure or interconnected files can be complex, especially for automated agents. Merging often requires careful manual reconciliation to ensure the integrity and consistency of the network's relationships. The longer a branch lives diverge from the main line, the more difficult this reconciliation becomes. Consider strategies like rebasing frequently or breaking down large changes to minimize merge conflicts.
*   **Separate Repository (Optional but Recommended):** For complex projects or larger teams, consider managing the context network in its own dedicated Git repository, linked via the `.context-network.md` discovery file. This isolates its history and simplifies version control management compared to mixing it with project artifact commits.
