# Software design and development

Follow the user journey from its entry point and inspect existing project conventions. Tie design decisions to concrete business constraints and describe what happens on failure. Reuse existing abstractions when they preserve the expected contract.

## Repairing an existing project

Start at the failing entry point. Read the version constraints, nearby implementation, callers, and relevant migration history. Preserve unrelated work in the checkout. Reproduce the symptom with a representative old record, client, or configuration when it matters. Capture the expected behavior from the contract or a known working path. With sparse tests, use a small fixture or a focused regression check. Record pre-existing failures separately.

Choose the simplest readable change that fixes the cause for supported inputs and keeps the security boundary intact. First consider the existing framework feature, query, or helper. Add a dependency, service, abstraction, or upgrade only when the current mechanism cannot meet a concrete requirement. If a larger change is necessary, identify that requirement and limit the change to it. Stop when the acceptance checks pass and the affected security properties hold.

Check the permitted path and the relevant failure or denial path. Preserve authorization, input validation, transactional integrity, and confidentiality as applicable. For older data with missing ownership or permissions, establish ownership from a trusted source or deny access until reconciled. Never broaden access or disable a protection to make a failing operation succeed. If a schema change is needed, test it on representative old data and check compatibility with still-supported readers and writers.

## Dependencies and verification

Before adding a dependency, verify the official project, distribution name, maintenance status, and version compatibility. Confirm API signatures against the installed version or its documentation. If verification fails, identify the uncertainty and look for a supported alternative already in the project.

Trace contract changes through callers and existing data. Validate inputs at trust boundaries, enforce server-side authorization for each resource, parameterize SQL, and encode output for its destination. Use the project's secret-management mechanism and check what responses and logs disclose.

For retryable or interruptible operations, state the property the system must preserve. If two confirmations arrive concurrently for one payment, check that the ledger records one credit and the balance changes once. Exercise migrations against pre-existing records.

Before destructive actions, verify the target and the authorization already granted. Test the affected behavior through its normal entry point and report what you observed.

Review generated changes for logic, configuration, security, and maintainability even when the demo works. Check that a maintainer can trace the failure path. Keep responsibilities clear, reuse existing logic, and introduce a new layer only when a concrete requirement warrants it. When citing Veracode, CodeRabbit, or package-hallucination studies, identify the sample, date, unit of analysis, and limits before quoting a rate. A finding about reviewed pull requests does not estimate the defect rate of a specific application.
