# Reference Prompt Rebuild Camera Video Gate

Purpose: stop using old camera / video shooting methods as the official standard
when the user provides a new high-quality reference prompt source.

This file controls how outside expert prompts are analyzed and converted into
`《棺中檀色》` production rules.

## 1. Core Rule

When the user provides a master / expert video prompt, do not copy its story,
characters, dialogue, worldbuilding, palette, or scene content.

Learn only the prompt engineering method:

```text
prompt structure
shot instruction grammar
camera clarity
motion wording
background / prop control
color control
continuity locking
negative constraints
AI stability wording
platform-specific compression
```

`《棺中檀色》` keeps its own:

```text
worldbuilding
characters
relationships
dialogue
事件顺序 / 사건 순서
color script
location logic
props
canon restrictions
```

## 2. Old Camera / Video Method Deprecation

Previous camera and video shooting method notes are now archived support only.
They must not be used as the final official camera / video prompt standard when
they conflict with this new rebuild workflow.

Do not delete old files unless the user explicitly asks for file deletion.
Instead, treat old camera / video rules as:

```text
legacy reference
failure history
comparison material
not final authority
```

The new official camera / video prompt method must be rebuilt from:

```text
1. User-provided expert prompt source.
2. Actual 분진 / shot sequence source.
3. Approved color script.
4. Approved colored BG / PROP reference images.
5. Canon character and worldbuilding rules.
6. Platform output rules for Jimeng / Seedance / Liblib / LibTV.
```

## 3. Expert Prompt Analysis Workflow

When the user gives an outside expert prompt, analyze it in this order:

```text
1. Separate content from method.
2. Mark content that must not be copied.
3. Extract reusable prompt grammar.
4. Extract camera / action wording patterns.
5. Extract background / prop stability wording.
6. Extract color / lighting continuity wording.
7. Extract platform-specific compression style.
8. Convert only the reusable method into 《棺中檀色》 templates.
```

Output format:

```markdown
## Expert Prompt Method Extraction

- Do not copy:
- Useful structure:
- Camera wording to learn:
- Motion wording to learn:
- Background / prop control to learn:
- Color control to learn:
- AI stability wording to learn:
- Must adapt for 《棺中檀色》:
- Rejected / unsafe for our project:
```

## 4. Rebuilt Prompt Template Requirement

After analysis, create a project-specific template. The template must use our
source and never the outside prompt content.

Required template layers:

```text
Source lock
Canon character lock
Approved color script lock
Approved BG / PROP reference lock
Camera function
Actor movement / blocking
Dialogue / voice direction
Prop reveal timing
Continuity anchor
Platform-specific output format
Forbidden deviations
```

## 5. Camera / Video Rule Replacement

For future split storyboard and video prompt work:

```text
Old camera method = not final.
New reference-prompt-derived method = candidate.
Candidate becomes official only after user approval.
```

Before approval, present:

```text
Old method problem / New method benefit / Risk / 적용 예시
```

Do not silently replace the story or camera logic in an active CUT. Always show
what changes in the prompt method, not in the source event.

## 6. Link With Color And Background Gates

This rebuild gate must run after:

```text
36_color_script_reference_image_gate.md
37_colored_background_prop_split_gate.md
```

The expert prompt method cannot override approved color or background logic.

Video prompt order:

```text
1. Read 분진 source.
2. Confirm color script.
3. Confirm BG / PROP references.
4. Analyze expert prompt method.
5. Rebuild our camera / video prompt method.
6. Generate final platform prompt.
```

## 7. Self Check

Before using any outside prompt method, check:

```text
[ ] Did I avoid copying outside story / character / dialogue / palette?
[ ] Did I extract only prompt structure and filming grammar?
[ ] Did I keep 《棺中檀色》 canon and source event order?
[ ] Did I use the approved color script and BG / PROP reference?
[ ] Did I mark old camera/video methods as legacy when they conflict?
[ ] Did I ask user approval before making a new method official?
```

If any answer is no, stop and redo the extraction.
