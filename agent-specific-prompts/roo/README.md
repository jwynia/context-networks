# Roo Modes
The prompts in this folder are the current ones I use to override the full prompt for the built-in modes. 

Doing that is found in Roo's Prompts tab, under the expandable "Advanced: Override System Prompt" section. There's a link in there, you can click and it will create a file in the .roo folder for the prompt you're looking at. You can use the copy button next to the "Preview System Prompt" to get what's currently in that prompt. If you've already customized your prompts for the core four Roo prompts, you absolutely should do this to keep those things.

** Only use the prompts in this folder directly if you haven't customized your Roo modes already **

Once your Roo modes are in actual files in the project via overrides, you can use Roo or other agents to add instructions to them for using the context network. In my experience, specifically asking for what to ADD makes a difference. Asking an agent to alter a prompt (especially its own) puts you in really weird territory, but asking it to actually rewrite it often leads to losing all tool use or similar messes. So, ask for a plan for how it *would* alter it before letting it.

I haven't done it, but have thought about setting Roo rules so that the .roo folder is restricted from all modes but a specific one that's locked down to implement (and check for risks) plans. I'd love to see someone try that and contribute it.