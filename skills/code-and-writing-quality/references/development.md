# Software design and development

Follow the user journey from its entry point and inspect existing project conventions. Tie design decisions to concrete business constraints and describe what happens on failure. Reuse existing abstractions when they preserve the expected contract.

Before adding a dependency, verify the official project, distribution name, maintenance status, and version compatibility. Confirm API signatures against the installed version or its documentation. If verification fails, identify the uncertainty and look for a supported alternative already in the project.

Trace contract changes through callers and existing data. Validate inputs at trust boundaries, enforce server-side authorization for each resource, parameterize SQL, and encode output for its destination. Use the project's secret-management mechanism and check what responses and logs disclose.

For retryable or interruptible operations, state the property the system must preserve. If two confirmations arrive concurrently for one payment, check that the ledger records one credit and the balance changes once. Exercise migrations against pre-existing records.

Before destructive actions, verify the target and the authorization already granted. Test the affected behavior through its normal entry point and report what you observed.

Review generated changes for logic, configuration, security, and maintainability even when the demo works. Check that a maintainer can trace the failure path. Keep responsibilities clear, reuse existing logic, and introduce a new layer only when a concrete requirement warrants it. When citing Veracode, CodeRabbit, or package-hallucination studies, identify the sample, date, unit of analysis, and limits before quoting a rate. A finding about reviewed pull requests does not estimate the defect rate of a specific application.
