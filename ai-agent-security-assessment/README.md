# AI Agent Security Assessment

An instruction-based skill for assessing an AI agent before granting access to email, files, browser sessions, secrets, or other accounts.

**Interview → verify evidence → model threats → test boundaries → recommend controls → retest.**

Use it for a personal assistant, a workplace agent, or an agent you are building. The procedure is product-neutral and NIST-informed. It is an assessment workflow, not a security enforcement service or compliance certification.

## What it includes

- A security and privacy questionnaire with follow-up questions.
- An evidence ledger separating agent claims, vendor documentation, user observations, configuration, and corroborated tests.
- Eleven controlled tests for approvals, denial, timeout/retry, scope binding, prompt injection, phishing, classification, persistence, audit, revocation, skill integrity, and account settings.
- Qualitative risk guidance and supported control recommendations.
- A report template with findings, remediation owners, acceptance tests, and residual uncertainty.

## Repository layout

The installable skill is in **`skills/assess-ai-agent-security/`**. Install that entire folder, including its `references`, `assets`, and `agents` directories. The repository root contains this README, the MIT license, and publishing instructions.

## Use without installing

Open `skills/assess-ai-agent-security/SKILL.md` and follow the linked questionnaire and test catalog manually. Alternatively, provide the complete skill folder to an assistant that can read attachments and ask it to follow the assessment procedure.

Uploading files or mentioning a skill name does not automatically install it. Keep all referenced files available to the assistant. If it cannot inspect your agent or settings, use documentary or guided mode; do not interpret that output as independent validation.

## Install in Codex CLI or a compatible local host

For Codex user-level discovery, copy the entire skill directory into `~/.agents/skills/assess-ai-agent-security/`. For a project-specific installation, place it in `.agents/skills/assess-ai-agent-security/` within the project.

After the host recognizes the skill, use:

> Use $assess-ai-agent-security to assess my AI agent before connecting email. Start in documentary mode, verify claims, and produce a controlled test plan. Do not send messages, change accounts, or delete real information.

You can also ask the available Skill Installer to install from this repository's `skills/assess-ai-agent-security` directory, providing your actual repository URL. Installation support varies by host; consult its current documentation.

## Use in ChatGPT

GitHub publication does not automatically install this skill in ChatGPT. To make it an installable ChatGPT experience, package it in a plugin and distribute it through a supported sharing or marketplace flow. Availability and permissions depend on the account/workspace.

Where skill-file import is supported, provide the complete skill folder and explicitly request installation. Once available in the selector, choose it with `@`. Do not assume a bare `$` name will resolve on every surface.

## Example requests

**Before connecting accounts**

> Assess an assistant I want to use for email summaries. I have not connected my mailbox. Ask the minimum scope questions, build a capability inventory, and identify evidence needed before granting access.

**Challenge an agent's claims**

> The agent says every send requires approval, but the documentation mentions persistent grants. Review these supplied artifacts, label their evidence strength, and propose a bounded test using a disposable mailbox. Do not run the test yet.

**Retest a control**

> Help me test deletion approval on a disposable note. Explain the expected result and what records would corroborate prevention. Stay in guided mode and do not delete genuine information.

## What a result means

| Result | Meaning |
| --- | --- |
| Pass for tested condition | Evidence supports the expected outcome in the specified scenario and scope. |
| Fail | Observed behavior contradicts the expected outcome. |
| Inconclusive | Evidence cannot establish the outcome, such as a send timeout without delivery records. |
| Not tested / blocked / not applicable | The assessment has not established effectiveness for this case. |

An approval dialog proves it was presented; it does not by itself prove prevention. A simulated phishing alert is a demonstration, not a measured detection rate. A setting can be configured without its effectiveness being tested.

## Test boundaries

Use synthetic content and owned disposable resources. Scope any live action in advance, including harmless test delivery if a sending control fails. Never supply real credentials or one-time codes, click suspicious links, disable protections, or run unreviewed attachments.

The skill cannot grant itself access, enforce platform permissions, establish continuous monitoring, or guarantee safety. Same-agent self-review has limited independence. Verify consequential action outcomes in the source service or host records. Preserve evidence before destructive cleanup.

## Expected outputs

A use-case decision, capability inventory, evidence ledger, findings and risk reasoning, test records, prioritized remediation, acceptance tests, and limitations. The assessment template is in `skills/assess-ai-agent-security/assets/assessment-template.md`.

## Publish this repository on GitHub

1. Extract this ZIP on your computer.
2. Create a repository named `ai-agent-security-assessment`; choose Public only if you intend everyone to access it.
3. In the repository, choose **Add file → Upload files**.
4. Upload the contents inside the extracted top-level folder: `README.md`, `LICENSE`, `.gitignore`, and the entire `skills/` folder.
5. Save the changes and check that `skills/assess-ai-agent-security/SKILL.md` and its supporting files are visible.
6. Share your repository URL with a sample request from this README.

Upload the extracted files rather than only the ZIP so readers and compatible installers can access the skill structure. GitHub publication shares the procedure, not your installed account state, connected accounts, or private assessment records.

## Maintenance and validation

The skill passed its creator's manifest/resource checks and a documentary forward-test using incomplete approval, timeout, MFA, and simulated-alert evidence. This does not validate any particular agent's runtime controls. Retest when workflows, model/app versions, connectors, grants, or skill contents change.

Review contributions for unsafe actions, unsupported product claims, overstated results, missing evidence requirements, and unauthorized scope expansion. Keep personal logs, screenshots, tokens, and real email content out of this repository.

## References

- [NIST SP 800-30 Rev. 1](https://csrc.nist.gov/pubs/sp/800/30/r1/final)
- [NIST Cybersecurity Framework](https://www.nist.gov/cyberframework)
- [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
- [OpenAI skill documentation](https://learn.chatgpt.com/docs/build-skills)

Framework mappings are guidance, not certification. Verify current editions and product-specific documentation when assessing a live system.

## License

MIT. See `LICENSE`. You may use, modify, and redistribute the project subject to the license terms.
