# Verification for complex work

Start with the acceptance condition in the user's terms. For each material assumption, choose evidence independent of the generated answer. Treat generated tests and summaries as hypotheses until they have been checked against the business rule or source. Prioritize failures that would change a decision, expose data, or corrupt state.

## Software checks

| Trigger | Check | Evidence to retain |
|---|---|---|
| A dependency is unfamiliar | Verify its distribution name and publisher through the upstream project, then check the installed or locked version. A successful install alone cannot establish provenance. | Upstream reference, version, and confirmed API signature. |
| The user proposes a design | Test a premise that could invalidate it. If a queue is proposed, trace what happens between committing data and publishing the event. | One concrete failure scenario and the resulting design decision. |
| A change crosses services | Trace caller, payload, consumer, and final persisted state. Include existing clients or records when the contract changes. | A representative request, response, and resulting state. |
| An operation can time out, repeat, or run concurrently | Exercise those paths where practical. A timeout after an external provider accepts a payment leaves its outcome uncertain. Verify reconciliation before permitting a second charge. | Final ledger balance, number of effects, and recovery outcome. |
| A route handles user-owned data | Check authorization for the resource on the server. Test with two separate test accounts and verify the permitted scope for each. | Expected access decisions and confirmation that sensitive fields stay out of logs. |
| An agent can modify live state | Resolve the actual target and operation from the configuration. A proposed migration and its execution require distinct scope checks. Prefer a disposable fixture for validation. | Target, authorization for the action, and execution status. |
| A generated change passes its own test | Check whether that test would fail on the original defect. Verify the user-visible outcome through the normal entry point. | A reproducible before/after result or a precise explanation of the remaining uncertainty. |

## Writing and retrieval checks

| Trigger | Check | Evidence to retain |
|---|---|---|
| A claim cites a publication | Open the work, check its identity, locate the supporting passage, and compare population, period, units, and strength of conclusion. A valid DOI can lead to an unrelated article. | Location and scope of the passage, or a qualification if unavailable. |
| A retrieval-based answer cites a document | Separate retrieval relevance from support for the answer. Examine whether the passage establishes the requested fact and whether the sources disagree. | Passage supporting each consequential claim or an explicit evidence gap. |
| A draft claims consensus or causation | Identify who expressed the view and which design supports the inference. Keep interviews, correlations, and causal evidence distinct. | Wording consistent with the actual evidence. |
| A draft feels generic | Look for unsupported significance, interchangeable conclusions, repeated rhetorical patterns, and attribution to unnamed experts. Replace these with grounded detail when available. Preserve correct, idiomatic prose. | A revision that adds information or improves clarity. |
| Someone asks whether AI wrote a text | Distinguish stylistic observations, a detector's classification, and a provider-specific watermark. Consider false positives and negatives. Check the language and genre represented in any evaluation. A missing watermark is inconclusive. | A bounded statement of what the available evidence supports. |
| A response is repetitive or aberrant | Inspect the concrete input and output. Repetition alone cannot identify a tokenizer issue or establish authorship. | Observed behavior and a clear distinction between diagnosis and conjecture. |

## Research background

The following pages explain the phenomena behind these checks. Consult original studies for numerical claims and limit each result to the models, datasets, or languages tested.

- [Package hallucinations and slopsquatting](https://en.wikipedia.org/wiki/Slopsquatting)
- [Vibe coding](https://en.wikipedia.org/wiki/Vibe_coding), [automation bias](https://en.wikipedia.org/wiki/Automation_bias), and [sycophancy](https://en.wikipedia.org/wiki/Sycophancy_%28artificial_intelligence%29)
- [Editorial observations on AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing)
- [AI content detection](https://en.wikipedia.org/wiki/Artificial_intelligence_content_detection) and [watermarking](https://en.wikipedia.org/wiki/AI_watermarking)

## Interpreting detector claims

Perplexity describes how predictable a passage is to a particular language model. Burstiness refers to variation across a passage and may be operationalized differently by different tools. When discussing GPTZero or a similar detector, identify the version and documented signals if available. Compare the evaluated language, genre, text length, and editing history with the actual passage. Standardized prose and some non-native English writing can be flagged incorrectly. Avoid inferring neurodivergence or assigning a subgroup-specific error rate without data for that population.

A watermark detector looks for a signal introduced during generation. Examples include token-list schemes described by Kirchenbauer and colleagues and sampling-based approaches such as SynthID-Text. For any named scheme, including textGrain, verify the original specification, detection access or key requirements, and the exact meaning of any distribution-preservation claim. A short excerpt, paraphrase, translation, or human edit may weaken the signal. Report what was measured and the uncertainty. A positive result for one passage does not establish who wrote or edited the whole document.

When assessing supposed glitch tokens, record the input, model and tokenizer versions if known, and whether the behavior reproduces in an isolated example. Treat the cause as unresolved if the observations do not distinguish tokenization from an ordinary generation error.
