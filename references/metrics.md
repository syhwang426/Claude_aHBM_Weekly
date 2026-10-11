# Measurement contract
One unit of delivery is an approved deliverable with explicit acceptance criteria, not a commit or Jira ticket count. Deduplicate multiple issues, MRs and commits linked to the same deliverable.

- **Verified weekly attainment:** sum of approved scope weights for planned deliverables Released & Verified by cutoff / sum of approved planned scope weights.
- **Integration attainment:** sum of integrated planned weights / sum of integration-target weights.
- **Evidence coverage:** deliverables with all required traceable evidence / reported deliverables.
- **Release validation:** passed required applicable checks / required applicable checks. Report failed mandatory gates separately; a high percentage never overrides a failed mandatory gate.
- **Blocker age:** cutoff timestamp minus blocker-opened timestamp; retain active/closed state.

For every percentage show numerator, denominator, baseline and timestamp. If denominator is zero/missing, show N/A. Scope added or removed after baseline must appear separately.

Status precedence: Released & Verified (accepted release + proven artifact SHA/digest + required gates passed); Integrated (code present in integration build but not fully released/validated); Implemented (merged or otherwise accepted implementation, not integrated); In Progress; Blocked; Unverified (claim lacking necessary proof). Blocked may be displayed as an additional risk flag even for partially implemented work.

Show raw commit/MR counts as optional activity context only; do not equate with value or rank people.
