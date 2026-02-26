# Agent Tools

This is a collection of reusable tools for AI-powered coding agents — currently focused on [Cursor](https://cursor.com) and adopted specifically for the designer workflow, where one needs sometimes no only to write a code, but also to do discovery work and analyze product solutions. These are commands and workflows I use day-to-day to make my work with agents more efficient. They are project-agnostic and designed to be dropped into any codebase.

## Table of contents

- [Commands](.cursor/commands/README.md) — slash commands for common agent workflows
- tbd

## Usage

### Quick install (recommended)

Open the terminal in your project's root folder and run:

```bash
npx @ek-so/agent-tools install
```

This copies all the shared tools into your project's `.cursor/` folder. Cursor picks them up automatically — no extra configuration needed.

### Getting updates

When new commands are added or existing ones are improved, run:

```bash
npx @ek-so/agent-tools update
```

That's it — your commands are up to date.

### Manual download

You can also just download the `.cursor/` folder from this repo and drop it into your project root (open [agent-tools](https://github.com/ek-so/agent-tools), click Code → Download ZIP). This works fine, but you won't get any future updates automatically — you'd need to re-download manually each time.

### Alternative installation with git subtree

If you'd rather not use npm and still want to get updates, you can use <code>git subtree</code> to pull folders directly from this repository. This lets you integrate just the parts you need into your own project and easily keep them up to date with a couple of simple commands.

<details>
<summary><strong>Instructions</strong></summary>

**Step 1.** Open the terminal in your project's root folder.

**Step 2.** Connect your project to this repo (once per project):

```bash
git remote add agent-tools git@github.com:ek-so/agent-tools.git
```

This saves a bookmark so git knows where to find this repo. Nothing visible changes in your project yet.

**Step 3.** Pull the folder you want:

```bash
git subtree add --prefix=.cursor agent-tools main --squash
```

This downloads the `.cursor/` folder into your project and creates a commit.

**To get updates later:**

```bash
git subtree pull --prefix=.cursor agent-tools main --squash
```

**Good to know:**

- **Don't edit the pulled files in your project.** They come from this shared repo. Treat them as read-only — if something needs changing, update it here in agent-tools instead.
- These commands won't break your project. If you see an error, paste it into Cursor chat — it can usually help.
- You can always delete the pulled folders, then commit, and then add them back fresh.

</details>
