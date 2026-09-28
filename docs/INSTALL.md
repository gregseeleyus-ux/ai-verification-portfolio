# Installing the skills

Each folder under skills/ is one skill. The file Claude reads is SKILL.md.

## Claude (web, desktop, or mobile)

1. Zip the skill folder (for example skills/guardian-context) so the zip contains SKILL.md at its top level or inside the folder.
2. In Claude, open Settings, then Capabilities (or Customize), then Skills, and upload the zip.
3. Install guardian-context first. The other skills tell Claude to load it before they run.
4. Turn the skill on. Claude uses it when your request matches its description; you can also name it ("run fresh-verify on this").

Menu names change over time; if these steps do not match what you see, search Claude's help center for "skills".

## Claude Code

Copy a skill folder into ~/.claude/skills/ (personal) or .claude/skills/ inside a project.

## After installing

- Copy the templates you need out of templates/ into your own workspace and rename them (for example SKILLS-RECORD.md).
- Run each skill on one real task before you rely on it, and log the result.
