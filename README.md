# nStudio
Reads your open place, writes the Luau, builds the instances, and makes every animation and sound in that place yours.

## What it does

nStudio is a local desktop companion for Roblox Studio with a built-in AI pair programmer.
Instead of starting from a blank editor, the AI can see the place you already have open, understand its structure and existing code, and use that context to build what you ask for.

### Build

Open Roblox Studio and nStudio side by side, then describe what you want.

> Make a platform that damages whoever steps on it, then disappears for 3 seconds.

nStudio reads the tree of your place — services, models, GUIs, scripts, and their source code.

The AI uses that context to generate a complete, reviewable change:

* the required instances
* their properties and configuration
* the scripts and where they belong
* the complete Luau implementation

The result isn't just a code snippet. It is a proposed change to your actual place.

Every proposal is presented as a card with the generated code visible and an explicit **Apply** button.

**Nothing enters your game without that click.**

When you apply a proposal, the entire change is committed to Studio as a single undo waypoint.

### AI

The AI is built into nStudio and works with the provider you choose.

Supported providers include:

* Anthropic
* OpenAI
* B.AI
* Groq
* OpenRouter
* Ollama
* OpenAI-compatible APIs

Bring your own API key and use the model that fits your workflow.

Your API key is stored in the operating system's credential vault. AI requests are sent directly from nStudio to the provider you configured.

**No nStudio account is required.**

### Assets

An asset only behaves as yours when the account behind the experience owns it.

nStudio can scan your place for referenced assets, including:

* animations
* sounds
* decals
* textures
* mesh textures
* particles
* interface images
* asset IDs referenced inside scripts

It can download those assets, re-upload them through Roblox Open Cloud under your account or group, and replace the original IDs with the new ones.

The entire operation is handled as a single undoable change.

Animations, sounds, images, and meshes all live in the same asset workspace. Switch between asset types, select exactly what you want to process, and keep a separate run history for each type.

Each run shows its progress as it happens. Completed runs can be reapplied or reverted from their history.

If an asset cannot be fetched, nStudio reports what failed, which side rejected the request, and the relevant Roblox response.



## Why it is built this way

**No nStudio account.**
nStudio runs locally on your machine. There is no nStudio account and no nStudio server required for the application to work. The Studio plugin connects directly to the local app through `127.0.0.1`.

**Your key.**
You bring your own API key. Credentials are stored in the operating system's secure credential vault, and requests go directly to the provider you selected.

**You review first.**
The AI proposes changes. You see the code, understand what will be changed, and decide whether to apply it. Human review is part of the workflow, not an optional setting.

**Native Studio tools.**
nStudio can work alongside Roblox Studio's built-in MCP server, giving the agent access to native Studio capabilities such as running Luau, reading the live DataModel, inspecting the place, capturing the viewport, and inserting assets.

You can also connect other MCP servers through local processes or streamable HTTP.

## Setup

### 1. Install nStudio

Download the latest release.

| Platform | Package                                  |
| -------- | ---------------------------------------- |
| Windows  | `.exe` installer                         |


### 2. Choose what you want to use

On first launch, nStudio lets you configure the features you need:

**AI**
Configure an AI provider and start building with natural language.

**Assets**
Configure Roblox access and manage assets without needing an AI provider.

You can configure either feature later from the application.

### 3. Configure your AI provider

Choose from:

* Anthropic
* OpenAI
* B.AI
* Groq
* OpenRouter
* Ollama
* OpenAI-compatible APIs

Enter your API key and select the model you want to use.

The key is stored in your operating system's credential vault.

There is no nStudio account or cloud login required.

### 4. Connect Roblox Studio

Open Roblox Studio and the place you want to work on.

Then go to:

**Game Settings → Security → Allow HTTP Requests**

Enable **Allow HTTP Requests**.

Open the **Plugins** tab and launch the **nStudio** plugin.

The plugin connects to the local nStudio application through `127.0.0.1`.

### 5. Start building

Open nStudio and describe what you want to build.

For example:

> Create a sword that deals 25 damage, has a 1-second cooldown, and plays a swing sound when activated.

nStudio reads the current place and generates the required instances and Luau.
Review the proposal, inspect the generated code, and click **Apply** when you're ready.

---

## Roblox Studio MCP

nStudio can also work with the MCP server built into Roblox Studio.
With Studio MCP enabled, the agent can interact with the live Studio environment and use native capabilities such as:

* running Luau
* reading the live DataModel
* inspecting the current place
* capturing the viewport
* inserting assets
* interacting with Studio tools

This is separate from the reviewed Build workflow.

The Build workflow is designed around explicit proposals and user approval, while MCP can be used when you want the agent to interact more directly with the running Studio session.

## Requirements

* Windows or macOS
* Roblox Studio
* An API key from a supported AI provider for AI features
* **Allow HTTP Requests** enabled in Roblox Studio
* A Roblox account with permission to modify the target experience

---

## License and notices

nStudio is proprietary software. All rights reserved.
nStudio is an independent project and is **not affiliated with, endorsed by, or sponsored by Roblox Corporation**. Roblox and Roblox Studio are trademarks of Roblox Corporation.
You are responsible for ensuring that you have the necessary rights and permissions to modify, use, upload, or re-upload any place or asset processed through nStudio. This includes complying with the **Roblox Terms of Use** and any other applicable policies.
nStudio does not grant ownership or usage rights to third-party content. Use it only with places, assets, and accounts you are authorized to access and modify.
