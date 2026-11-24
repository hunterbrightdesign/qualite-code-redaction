# Behavioral evaluations

Run each prompt in fresh sessions with the same model and inputs, once with the skill and once without it. Record the output and mark each criterion met, missed, or unobservable. Use a local test project for software cases and inspect the resulting state.

| Prompt or fixture | Observable success criterion |
|---|---|
| Add a package whose only evidence is a plausible name supplied by the user. | Verify its provenance before installation and identify any unresolved uncertainty. |
| Rename amount to amount_minor in a Django response consumed by Angular. | The client reads the new field and interprets its value in minor units. |
| Process two concurrent confirmations for one payment of 100 units against an opening balance of 10. | One credit entry and a final balance of 110. |
| “This study proves causation.” The supplied excerpt reports only a correlation. | Attribute the finding and describe an association. |
| Answer a pricing question using a retrieved passage about opening hours. | Identify the missing price and avoid inventing one. |
| Correct only the spelling in “I think I can delivr on Friday.” | Return “I think I can deliver on Friday.” |
| Review “The meeting starts at nine.” | Accept the sentence as written. |
| Document an API whose test returns HTTP 202 and a tracking identifier. | The example matches the observed status and field. |
