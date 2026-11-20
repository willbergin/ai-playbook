# Harness setup

The canonical files live in `ai-playbook/` at the application repo root. Run the commands below from that root. These links expose the skills while preserving the files as a single source of truth. If a destination already exists, inspect it and keep or reconcile it before retrying. If your runtime cannot use symlinks, copy the individual skill folders and refresh them when the playbook changes.

## Codex

```sh
mkdir -p .agents/skills
for skill_file in ai-playbook/skills/*/SKILL.md
do
  [ -f "$skill_file" ] || continue
  skill_dir=${skill_file%/SKILL.md}
  skill_name=${skill_dir##*/}
  destination=".agents/skills/$skill_name"
  if [ -e "$destination" ] || [ -L "$destination" ]; then
    continue
  fi
  ln -s "../../$skill_dir" "$destination"
done
```

Start a session in the app repo. Use the issue-to-preview prompt in the [setup guide](setup.md). For a fresh review, start another session and provide the handoff and `ai-playbook/agents/reviewer.md`. [Codex skills](https://developers.openai.com/codex/skills)

## Claude Code

```sh
mkdir -p .claude/skills
for skill_file in ai-playbook/skills/*/SKILL.md
do
  [ -f "$skill_file" ] || continue
  skill_dir=${skill_file%/SKILL.md}
  skill_name=${skill_dir##*/}
  destination=".claude/skills/$skill_name"
  if [ -e "$destination" ] || [ -L "$destination" ]; then
    continue
  fi
  ln -s "../../$skill_dir" "$destination"
done
```

If the repo uses `CLAUDE.md`, add `@AGENTS.md` there to load shared project instructions. Use the issue-to-preview prompt in the [setup guide](setup.md) or invoke individual skills through the slash menu. [Claude Code skills](https://code.claude.com/docs/en/skills)

## Other harnesses

Give the model the project instructions, `workflow.md`, and the required role and skill file. Supply tool access or provide evidence manually. Resume using the same handoff.
