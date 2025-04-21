# Context Network Initialization
This is how I'm currently initializing these.

## Steps
1. I create an empty folder/git repo.
2. I create an "inbox" folder and place the Comprehensive Guide to Context Networks markdown document in there.
3. Using Cline's Plan mode, I run a prompt similar to this one. I change "software project" to something else if it is and I follow this with a paragraph describing the goal of the project.
    ```
    In the inbox folder is a guide to context networks. I want to create a context network folder and .context-network.md entry point for a software project. I will be providing additional documents from outside this project for integration into the context network after it is set up. They will always be dropped into the inbox folder. They should always be completely processed and integrated into the context network and then archived, leaving the inbox empty after integration.
    ```
4. If Cline's plan looks good, I flip it to act and let it set things up. Otherwise, I clarify the purpose of the project, tools I want to use. It's perfectly fine to say you'll provide that information later. Setting a context network up is not a one shot thing that locks you in. I've even taken an entire context network, renamed the folder to "archived-context" and started a new one and then asked agents to migrate information from the old one to a new one, reorganizing according to the new structure.
5. Commit your new context network. Version control is critical in working this way (see below)

For a fun bonus round, follow up with this prompt to get a context network more tuned to the project goals. 

```
Is there anything about the current design of the context network that should change to better suit the project goals? Better ways of linking information for dense and rapid navigation?
```
6. Put override copies of Roo's mode prompts into the project folder.
7. Brainstorm with Roo's Architect or Cline's Plan agents about any additional Roo modes that might make sense.
8. Start dropping documents into the inbox and talking with Architect/Plan agents about how to build