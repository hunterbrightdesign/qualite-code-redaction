# Code and Writing Quality

An agent skill for checking software changes, reviewing architecture, and editing text while preserving the author's meaning and voice.

## Install

With Node.js 22.20 or later installed, run this command from the project where you want to use the skill:

```sh
npx skills add hunterbrightdesign/qualite-code-redaction
```

Select **code-and-writing-quality** and the agents you use when prompted. Open a new session in your project. To check the installation, run `npx skills list`.

## Try it

- “Check whether this API response matches the fields its client reads.”
- “Fix the spelling in this message and keep the tentative delivery date.”

The [skill instructions](skills/code-and-writing-quality/SKILL.md) link to the development and writing guides. The [evaluation cases](evals/cases.md) describe how to check the results.

If you installed the earlier French version manually, remove its `qualite-code-redaction` entries from your project's skill directories after confirming that the English version is available.

For work spanning multiple systems or sources, the [verification guide](skills/code-and-writing-quality/references/verification.md) maps documented failure modes to checks and observable evidence.
