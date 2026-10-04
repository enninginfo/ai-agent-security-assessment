# Discovery questionnaire

Adapt to the use case. Ask the target to distinguish capabilities, actual permissions, unknowns, and evidence; do not assume introspection is accurate.

## Work and access
1. What tasks and exact data/actions are necessary?
2. Which connectors, browser sessions, files, memory, background jobs, tools, or APIs are currently reachable? Show a redacted inventory if available.
3. Can you read, send, share, modify, delete, or execute? Who enforces and can change permissions?
4. Are read/write separated? What narrow scopes exist? Can alternate tools/browser access excluded data?

## Identity and approvals
5. Which account authenticates the user, and does it support MFA/passkeys? Do not request secrets.
6. How are tokens/keys/sessions isolated, expired, and revoked? Can the model, generated code, plugins, or subagents access raw values?
7. Which actions require approval? Is it one-time, task/session/time-bound, or persistent?
8. Does approval bind action, resource, destination/recipient, payload, amount, and expiry? What happens on denial, cancellation, timeout, changed parameters, or retries?
9. Can chat or untrusted content authorize actions? Can the agent alter its policy?

## Privacy and lifecycle
10. Where does data go for storage, inference, telemetry, and support? What locations/subprocessors are documented?
11. What transit/storage encryption and key ownership are documented? What provider access remains?
12. Which staff/support roles can access content and under what controls? What is unknown?
13. What remains in chat, memory, files, logs, backups, and training pipelines? What do deletion and opt-out cover and within what periods?
14. Can inputs be restricted before ingestion? How are other people's information and authentication messages handled?

## Adversarial content and skills
15. How are instructions separated from emails/pages/files/images/tool output? What stops a trust-boundary crossing?
16. Can headers/source be inspected without opening links or executing attachments? Which fields are actually available?
17. Are phishing indicators treated as evidence rather than proof? How are uncertainty and benign cases handled?
18. Show claimed security skill files, sources, dependencies, permissions, invocation and change controls. Who can edit or execute them?

## Detection and recovery
19. What events are monitored, when, and how are alerts delivered? On demand, scheduled, or continuous? What is invisible?
20. Are requested, denied, expired, retried, and completed actions logged? What fields, retention, export, and integrity/access controls exist?
21. Can outcomes be verified in the source application independently? What corroborates non-execution?
22. How can users stop jobs, revoke grants/sessions, recover accounts, and preserve evidence? What copied data remains after disconnect?

For strong claims ask: “What exact source or setting supports this? What exceptions apply? Which bounded test could falsify it? What can you not verify?” Keep answers as claims until corroborated.

