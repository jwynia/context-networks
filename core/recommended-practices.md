# Recommended Practices for Context Networks

This document outlines key recommended practices for effectively creating, managing, and utilizing context networks, particularly for human users.

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
