# psychobiography

An agent skill for producing a psychodynamic read of a personal archive — a journal, diary, voice memos, or message history — covering themes, patterns, blind spots, and emotional arcs, with the epistemic discipline the task otherwise lacks. Every claim carries an evidence grade, every interpretation sits next to its flattest alternative, and the document ends with questions to sit with rather than verdicts.

It exists because the naive version fails in a measured direction: archives are rain gauges, not censuses — they over-record pain and under-record repair, routine, and warmth — and under a "be direct, don't flatter me" brief, model readers resolve every ambiguity toward indictment. The result is an eloquent, confident, wrong analysis that the subject experiences as an attack. The skill replaces that accidental cruelty with deliberate, visible generosity: evidence grading (narrated once / recurring / behavior-corroborated / behavior-contradicted), a ban on inference-from-absence and unfalsifiable moves, base-rate checks before any "signature" claim, triangulation against behavioral records when they exist (with grades capped honestly when they don't), a kindness gate — ambiguity resolves toward the generous reading, and a harsh claim must be behavior-corroborated to appear as more than a gentle question — and a visible-revision protocol for when the subject pushes back: margin verdicts of retained / weakened / withdrawn, with withdrawn text left legible under strikethrough.

## Install

**Claude Code** — clone straight into the skills directory; it auto-loads next session:

```bash
git clone https://github.com/henryaj/psychobiography ~/.claude/skills/psychobiography
```

(Use `<project>/.claude/skills/` instead for project scope; `git pull` to update.)

**Skills CLI** (cross-agent):

```bash
npx skills add henryaj/psychobiography --agent claude-code
```

The `--agent claude-code` flag matters: without it the CLI may only place the canonical copy in `~/.agents/skills/`, which Claude Code doesn't read — you want it in `~/.claude/skills/` (add `-g` for global, or run inside a project for project scope).

## Requirements

- A personal archive on disk (dated markdown files work best; voice-memo transcripts, chat exports, and imported posts all count)
- Optional but strongly recommended: a behavioral record to triangulate against — calendar history, attendance, files, commits — since narration alone is the skewed instrument the skill is built to correct for
- Any agent harness (built for Claude Code; no subagent support required)

## Usage

In Claude Code, invoke it as a slash command:

```
/psychobiography
```

A bare invocation reads the whole archive and produces the full analysis as a designed, self-contained HTML report — a preamble stating scope and method, evidence in your favor (early, not as an appendix), preoccupations and themes, arcs over time, narration-vs-behavior divergences (when a behavioral record exists), patterns, blind spots framed as gentle questions, and closing questions to sit with — with every claim graded and cited by dated quote. Add arguments to scope or shape it:

```
/psychobiography the journal/ folder, 2020–2024 only
/psychobiography focus on relationships; plain markdown instead of HTML
```

It also governs the aftermath, which is where these documents live or die: when the subject pushes back on a finding, the skill verifies against the archive before conceding or holding, weaves revisions in visibly rather than silently patching, and on request runs a full adversarial self-audit — re-examining every principal claim and publishing per-claim verdicts. A fair warning belongs here as much as in the skill: this genre is personal, and even the calibrated version can sting. Be deliberate about what you ask for.

## License

MIT
