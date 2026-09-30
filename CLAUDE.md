## Role

Claude is responsible for analyzing the Zoho Creator application source provided in `raw/`, extracting its structure and implementation details, and maintaining the corresponding documentation and code modules.

## Objective

Convert the raw Zoho Creator application source into an organized, maintainable project structure while preserving the application's actual forms, workflows, functions, schedules, connections, permissions, and related implementation details.

## Folder Structure

``` 
raw/  --- Source documents managed by the user

workflow/ --- Application workflows and relationships managed by Claude, including Mermaid diagrams connecting forms, functions, schedules, and other application components

code modules/ --- Zoho Creator code and configuration modules managed by Claude, including forms, schedules, custom functions, record functions, connections, and related modules

testing/ --- QA/test-engineering risk repository managed by Claude: edge cases, defects, risks, and test gaps found by reviewing `code modules/`/`workflow/` against the source in `raw/`, organized by application domain and by risk category

fixes/ --- remediation tracker managed by Claude: one file per Test ID tracking the fix approach and status (Proposed/Approved/Applied to raw/Applied to code modules/Verified) for every finding in `testing/` (as of 2026-09-10, per user instruction — every Test ID gets a file, most sitting at Proposed until picked up, not just ones actively being resolved)
```

```
raw/
└── <source document>

workflow/
├── application-overview.md
├── data-flow.md
├── form-workflows/
├── function-workflows/
└── diagrams/
    ├── *.mmd inside .md for obsidian to render (sequence/state/flow diagrams per form or process)
    └── data-model-erd.md --- field-level entity-relationship diagram: every form as an entity with its key/lookup fields, connected to other forms via the specific lookup field or automation write (not generic form-to-form arrows)

code modules/
├── forms/
├── reports/
├── functions/
│   ├── deluge/
│   └── record-functions/
├── schedules/
├── connections/
├── workflows/
└── permissions/

testing/
├── README.md --- index of the finding set, severity/type key, how to use the repository
├── test-strategy.md --- the review methodology: coverage checklist, classification scheme, severity rubric, finding template
├── TODO.md --- master checklist tracking fixed/open status across every finding by Test ID
├── edge-cases/ --- organized by application domain (one subfolder per domain, e.g. leave/, timesheet/, assets/, consultant/, notifications/)
├── security/ --- access-control gaps, data exposure, wrong-user attribution
├── data-integrity/ --- stale/incorrect data, broken references, incorrect calculations, ledger/balance integrity
├── concurrency/ --- race conditions, idempotency, check-then-act logic, retry/re-run behavior
├── integrations/ --- Cliq/email/external-service reliability and failure handling
├── regression/ --- watchlist tied to renames/refactors, for re-testing when those areas change again
└── known-issues/ --- captured/unused fields, dead code, accepted-as-is anomalies not otherwise categorized

fixes/
├── README.md --- purpose, structure, and status lifecycle for tracked fixes
├── TODO.md --- master checklist tracking Proposed/Approved/Applied/Verified status across every tracked fix by Test ID
└── <TEST-ID>.md --- one file per finding being fixed: chosen/candidate approach, exact before/after code, locations affected (raw/ and code modules/), verification steps
```
## Scope

Claude works on the Zoho Creator application represented by the source files in `raw/`. The scope includes extracting and organizing application components such as forms, fields, reports, workflows, Deluge functions, record functions, schedules, connections, permissions, and application configuration.

Claude manages the derived documentation and code representation in `workflow/`, `code modules/`, `testing/`, and `fixes/`. The `raw/` directory remains user-managed and is treated as the source of truth.

In addition to extraction and documentation, Claude performs QA/test-engineering review of the extracted representation — acting as a senior developer and senior QA engineer trying to find how the implementation could fail, break, produce incorrect results, create inconsistent data, violate business rules, or expose data — and records findings under `testing/`. See **Operating Modes → Testing/QA Review** below.

Claude tracks the remediation for every `testing/` finding under `fixes/` (one file per Test ID: chosen/candidate fix approach, exact before/after code, affected locations in `raw/` and `code modules/`, verification steps) rather than resolving it silently inside `testing/`. As of 2026-09-10, this means every finding gets a `fixes/<TEST-ID>.md` file as soon as it's documented in `testing/` — most start at `Proposed` (a written fix approach, nothing changed yet) and only move further once someone actually picks the work up. A `Proposed` file is a pre-written plan, not a commitment to do the work. Findings that genuinely have no concrete fix yet (need a business-owner decision, or runtime verification first) say so explicitly in the file rather than inventing one, per the rule against inventing business requirements; accepted-as-design or test-planning findings say "no fix proposed" outright. A fix only reaches "Applied to raw/" status with the user's explicit instruction, since `raw/` remains user-managed. Once a fix is verified, update the fix's status in `fixes/`, flip the finding's `Status` field in `testing/`, and sync both `testing/TODO.md` and `fixes/TODO.md`.

## Core Instructions

- Treat `raw/` as the authoritative source. Do not invent application components, logic, relationships, or configuration that are not supported by the source.
    
- Preserve the exact Zoho Creator names used in the source, including form names, field link names, function names, schedules, connections, and other identifiers.
    
- Extract application components into logical, separate modules rather than keeping the entire application in one file.
    
- Maintain relationships between components so that dependencies and execution flow can be understood from the generated documentation.
    
- Use Mermaid diagrams in `workflow/` when a workflow or relationship is better represented visually.
    
- Maintain `workflow/diagrams/data-model-erd.md` as the field-level entity-relationship diagram of all forms: represent each form as an entity listing its key/lookup fields (not a single unlabeled box), and connect two forms only via the specific field that creates the relationship — a Creator picklist lookup (`values = OtherForm.ID`) or a documented automation write (schedule/on-success workflow insert) — never a generic, unlabeled form-to-form arrow. Update it whenever a form's lookup fields or automation writes change.
    
- Keep generated files organized according to the folder structure defined in this document.
    
- When the source changes, update the affected derived modules and workflows rather than creating duplicate representations.
    
- Do not modify files under `raw/` unless explicitly instructed by the user.

## Operating Modes

#### Extraction

Extract the application structure, configuration, fields, code, and other components from the source in `raw/` and organize them under the appropriate managed folders.

#### Documentation

Document relationships and execution flows between application components in `workflow/`, using Mermaid diagrams where appropriate.

#### Development

Create, update, analyze, or refactor the Zoho Creator modules stored under `code modules/` while preserving compatibility with the source application.

#### Testing/QA Review

Act as a senior software engineer and senior QA/test engineer reviewing the application as if responsible for maintaining it in production. Inspect the forms, reports, workflows, functions, schedules, and integrations captured in `code modules/`/`workflow/` (cross-checked against `raw/`) to identify how the implementation could fail, break, produce incorrect results, create inconsistent data, violate business rules, or expose data. Do not just explain what the code does — think like someone trying to break the system, and like someone designing tests that would catch real production failures. Do not assume unusual behavior is automatically a bug.

For every component reviewed, systematically check:

- Null, empty, missing, malformed, unexpected, minimum, maximum, and boundary inputs
- New records vs. existing records
- Creating, editing, reopening, submitting, approving, rejecting, cancelling, and resubmitting records
- Missing or deleted related records
- Duplicate records and duplicate submissions
- Date/time edge cases: yesterday, today, future dates, month/year boundaries, leap years, start/end of day
- Different users, roles, permissions, and users accessing another user's records
- State inconsistencies between fields
- Stale values remaining after a field changes
- Incorrect calculations, aggregations, deductions, or balances
- Partial execution and failed updates
- Retry behavior
- Functions/workflows being executed more than once
- Scheduled functions running multiple times
- Race conditions and check-then-act logic
- Idempotency
- API, email, notification, authentication, timeout, and external-service failures
- Security and unauthorized data access
- Broken references, renamed components, missing fields, dead code, and unreachable logic
- Interactions between different functions/workflows rather than reviewing each in isolation

**Classify every finding as one of:**

1. **EDGE CASE** — unusual but valid input/state that should be handled
2. **DEFECT** — the current implementation can produce incorrect behavior
3. **RISK** — the behavior depends on an assumption or runtime condition
4. **TEST GAP** — an important scenario is not explicitly validated

**Severity:**

- **CRITICAL** — data corruption, security exposure, wrong-user attribution, or workflow-breaking failure
- **HIGH** — major incorrect business result, stuck workflow, significant integration failure, or data exposure
- **MEDIUM** — meaningful issue with limited impact or a workaround
- **LOW** — minor issue, dead code, cosmetic issue, or documentation inconsistency

Never invent business requirements. Distinguish clearly between confirmed behavior from the code, reasonable inference, runtime-dependent behavior, and behavior requiring business-owner confirmation — and mark runtime-dependent findings explicitly as needing runtime verification. Do not modify source code (or `code modules/`/`workflow/` business logic) while performing a review, and do not silently fix issues — findings are documented in `testing/`, not resolved there. Not every observation is a defect; prioritize by actual technical/business impact, and look specifically for bugs that occur because multiple components interact (a function may be correct in isolation but create a state that breaks a different workflow later).

**Documentation structure** (see `testing/` in Folder Structure above): organize findings primarily by application/component/domain (e.g. `edge-cases/leave/`, `edge-cases/timesheet/`, `edge-cases/assets/`, `edge-cases/consultant/`, `edge-cases/notifications/`), and use `security/`, `data-integrity/`, `concurrency/`, `integrations/`, `regression/`, `known-issues/` for findings that belong to those cross-cutting categories instead. Do not duplicate the same finding across multiple files — cross-reference by Test ID instead. Do not turn every observation into a defect, and do not produce one giant flat list.

**Every documented finding must contain:** Test ID (stable, e.g. `LEAVE-EDGE-001`, `SECURITY-001`, `CONCURRENCY-001`), finding name, Type, Severity, Component, Scenario, Preconditions, Steps to reproduce, Expected behavior, Actual/potential behavior, Impact, Root cause, exact source reference (`raw/Omm_Applications.md` line(s) and/or the `code modules/` file), Runtime assumption (if applicable), Related edge cases, Regression tests, and Status.

The resulting `testing/` repository should let a developer or QA engineer months later understand known risks, reproduce issues, run regression tests, review future changes, onboard onto the project, verify fixes, and identify untested scenarios.

`testing/TODO.md` is the fixed/open checklist for every Test ID — keep it in sync whenever a finding's `Status` changes (check/uncheck the box there when the finding's own `Status` field is updated, and vice versa). It does not replace the per-finding `Status` field; it's a rollup view over it.

## Input Handling

- Read the relevant source from `raw/` before extracting or modifying derived content.
    
- Identify the application-level configuration first, then identify individual application components.
    
- Distinguish between configuration, UI components, data components, executable code, automation, integrations, and permissions.
    
- Preserve source terminology and identifiers exactly.
    
- If information is incomplete or ambiguous, retain the ambiguity and do not infer unsupported behavior.
    
- When a request refers to a specific component, inspect its related dependencies before modifying its representation.
    

## Processing Workflow

### Step 1

Read and analyze the source document in `raw/`.

### Step 2

Identify and classify all relevant Zoho Creator application components and their relationships.

### Step 3

Extract the components into the appropriate locations under `code modules/` and document their relationships under `workflow/`.

### Step 4

Verify that the generated representation remains consistent with the source and report what was created or updated.

## Rules & Constraints

### General Rules

- Source-derived facts take precedence over assumptions.
    
- Do not silently change business logic while extracting or documenting it.
    
- Keep each module focused on one logical Creator component or component group.
    
- Preserve dependencies and references between modules.
    
- Avoid unnecessary duplication.
    

### Classification Rules

- Forms and their fields belong under `code modules/forms/`.
    
- Deluge custom functions belong under `code modules/functions/`.
    
- Record-level functions/actions belong under `code modules/functions/record-functions/`.
    
- Schedules belong under `code modules/schedules/`.
    
- Connections belong under `code modules/connections/`.
    
- Permissions and access configuration belong under `code modules/permissions/`.
    
- Workflows, relationships, execution flows, and Mermaid diagrams belong under `workflow/`.
    
- Source files remain under `raw/` and are not treated as Claude-managed modules.

- QA/test findings (edge cases, defects, risks, test gaps discovered by reviewing the application) belong under `testing/`, organized by domain first and by cross-cutting category (`security/`, `data-integrity/`, `concurrency/`, `integrations/`, `regression/`, `known-issues/`) when that fits better than a domain folder.

- Remediation tracking for a `testing/` finding (fix approach, status, before/after code, verification) belongs under `fixes/`, one file per Test ID — not folded into the `testing/` finding itself.
    

### Formatting Rules

- Use Markdown for documentation and Mermaid for diagrams.
    
- Use code blocks for Deluge and other source code.
    
- Use exact Creator identifiers in code and technical documentation.
    
- Keep filenames descriptive and consistent with the corresponding Creator component.
    
- Entity-relationship diagrams use Mermaid `erDiagram` syntax: list each form's key/FK fields as entity attributes (mark lookup fields `FK`), use solid lines for true Creator picklist lookups and dashed lines for automation-driven writes or non-lookup (string-matched) references, and label every connector with the source field name.
    

### Validation Rules

- Confirm that extracted names and identifiers match the source.
    
- Confirm that referenced components actually exist in the source before documenting them as dependencies.
    
- Confirm that code is placed in the correct module category.
    
- Do not claim that a workflow, function, or relationship exists when it cannot be established from the source.
    

## Output Requirements

- Produce organized files under the appropriate Claude-managed directories.
    
- Preserve the original implementation details when extracting code.
    
- Include relevant dependencies and relationships in component documentation.
    
- Create or update Mermaid workflow diagrams when they materially clarify application flow.
    
- Keep outputs directly traceable to the source in `raw/`.
    

## Decision Logic

1. Determine whether the requested information is present in `raw/`.
    
2. Identify the Creator component or components involved.
    
3. Determine the appropriate managed folder and module representation.
    
4. Identify dependencies and related workflows.
    
5. Extract or update the affected modules.
    
6. Update workflow documentation or diagrams when the component relationships change.
    
7. If the source does not provide enough information, state what is missing instead of guessing.
    

## Exceptions & Edge Cases

- If the same identifier appears in multiple contexts, preserve the source context and do not merge components without evidence that they are the same component.
    
- If a referenced component is missing from the source, document the unresolved reference rather than inventing the component.
    
- If source definitions conflict, preserve the source representation and flag the conflict for review.
    
- If a component contains embedded configuration, code, or automation, keep those details associated with the component while also extracting them into their appropriate module category when required.
    
- If a requested change would require information not present in `raw/`, ask for the missing source or explicitly identify the limitation.
    

## Examples

### Example 1

Extract a Creator form from `raw/` and create its corresponding form module under `code modules/forms/`, preserving its fields, field types, display names, validations, and actions.

### Example 2

Identify how a form, custom function, and schedule interact, then document the relationship in `workflow/` using a Mermaid diagram.

### Example 3

When a user asks to modify a Deluge function, locate the source definition and its dependencies first, then update the corresponding module under `code modules/functions/`.

## Do / Don't

### Do

- Do use `raw/` as the source of truth.
    
- Do preserve exact Creator identifiers.
    
- Do separate application components into logical modules.
    
- Do document important relationships and execution flows.
    
- Do flag uncertainty and missing information.
    

### Don't

- Don't modify `raw/` without explicit instruction.
    
- Don't invent missing Creator components or business logic.
    
- Don't rename Creator identifiers during extraction.
    
- Don't create unsupported dependencies or workflows.
    
- Don't overwrite unrelated modules when making a targeted change.
    

## Final Response Format

When completing a task, briefly state:

- What was analyzed or changed.
    
- Which managed files or folders were affected.
    
- Any unresolved references, missing information, or source conflicts.
    

## Change Log

Record significant structural or behavioral changes made to the Claude-managed representation of the application. Do not use the change log for routine analysis that does not modify managed files.

### 2026-09-09

- Added the **Testing/QA Review** operating mode and the `testing/` managed folder (structure, classification scheme, severity rubric, finding template) to this document, per user instruction.
- Performed the first full QA/test-engineering review of the application and populated `testing/` (`README.md`, `test-strategy.md`, and findings under `edge-cases/{leave,timesheet,assets,consultant,notifications}/`, `security/`, `data-integrity/`, `concurrency/`, `integrations/`, `regression/`, `known-issues/`). Superseded the ad hoc root-level `edge-cases/` folder from a prior session — its 21 findings were re-verified against `raw/` and folded into the new structure with stable Test IDs; several new findings were found in the same pass (see `testing/README.md` for the full index). The old root-level `edge-cases/` folder was deleted at the user's explicit request once the migration was confirmed complete.
- Corrected `code modules/workflows/Leave_Request-workflows.md`'s `Valid` rule: the extraction had omitted the source's `if(input.Balance_Deducted = false) { ... }` wrapper around the entire balance/half-day check (`raw/Omm_Applications.md` lines 5439-5457). This is a documentation-accuracy fix (the source did not change); see `testing/concurrency/race-conditions-and-idempotency.md` (CONCURRENCY-005) for the defect this uncovered.
- Added `testing/TODO.md`, a master checklist tracking every finding's Test ID against fixed/open status, grouped by severity, at the user's request.
- Added the `fixes/` managed folder (per user instruction) to track remediation of `testing/` findings separately from the findings themselves: `fixes/README.md` (structure and Proposed/Approved/Applied to raw/Applied to code modules/Verified status lifecycle), `fixes/TODO.md` (rollup checklist), and `fixes/DATA-001.md` (first tracked fix: two candidate approaches for reversing a rejected leave request's balance deduction — filtering `Type_field != "Reject"` at every read site vs. inserting an offsetting ledger row at the write site — awaiting user decision on approach and on whether/when to apply to `raw/`).

### 2026-09-10

- User edited `raw/Omm_Applications.md` directly and asked to sync the change. No git history exists for this project, so the sync was done as a full manual re-audit rather than a diff: five parallel domain passes (Leave; Timekeeping; Assets; Consultant/Client/Admin/permissions/connections; the cross-cutting Deluge helper/notification function library) each re-read their slice of `raw/` in full and reconciled it against `code modules/` and `workflow/`, updating source-line citations throughout (the file's overall section ordering shifted by hundreds to ~1500 lines — a regenerate, not a targeted edit) and correcting the content wherever it had actually changed.
- **Real behavior changes found and synced** (not just line-number churn):
  - `Leave_Request.pre_fil_few_fields` and `Timekeeping1.Load` now guard `Consultant_Name` reassignment with `if(input.Consultant_Name == null)` (previously unconditional every load) — fixes CONSULTANT-EDGE-001 on these two forms; the three asset forms (`Add_Asset`, `Asset_Return_Form`, `Asset_Return_Inspection_Form`) were verified unchanged and still open for this issue.
  - `Cliq.Send_Leave_Rejected_Notification` now inserts an offsetting `Leave_Balance_Record` row instead of relabeling the original in place — correct on its own (Option B of `fixes/DATA-001.md`, applied by the user directly to `raw/`). But three of four balance-summing sites (`get_balance_html`, `Leave_Request.Valid`, `pre_fil_few_fields`'s inline table) were *also* given a `Type_field != "Reject"` filter in the same update, which excludes the new offsetting row while still counting the untouched original deduction — so those three sites still show/enforce the reduced balance after a rejection. Only the fourth site (the portal `Leave_Balance` page, left unfiltered) shows the correct, restored balance. **A first sync pass mischaracterized this as "3 of 4 sites fixed, 1 remaining" — that had the filter's effect backwards and was corrected the same day**: DATA-001 remains fully **Open**, not partially fixed (see `testing/data-integrity/balance-ledger-integrity.md` for the worked example and `fixes/DATA-001.md` for the corrected recommended fix — remove the filter from the three sites rather than adding it to the fourth).
  - `Timekeeping1`'s `P1_Hours_Worked_Start_Tim`/`P2_Hours_Worked_End_Time` regained future-time guards (removed in an earlier pass); `Hours_Worked` computation moved entirely into `P2`, which introduced a new defect (`P2`'s future-clamp branch never recomputes `Hours_Worked` — new finding TIMESHEET-EDGE-007). TIMESHEET-EDGE-001 narrowed accordingly (only `Work_Day`'s own future-date guard remains disabled) and was downgraded from MEDIUM to LOW.
  - `asset_approver`'s profile permissions are no longer identical to `consultant`'s (gained `Create,Viewall,Tab` on `Asset_Return_Inspection_Form`) — SECURITY-002's premise updated, not closed (still no explicit approve/reject action exists).
  - `Add_Consultant.Email` now has a `unique` constraint, confirming the DATA-002 fix (`F.UF()`'s `count() >= 1` guard) is live in `raw/`.
  - `Asset_Return_Form`'s `Reciept_ID` prefix changed to match `Add_Asset`'s (`"OMM-ASSET_REP/NEW-"`, was `"OMM-ASSET_RET-"`) — new finding DATA-009, compounding DATA-008.
  - Minor: `Asset_Return_Form.Hiding_few_fields_on_load2` hides a nonexistent field `plain2` (dead reference, added as DATA-005 Item D).
- Updated `testing/` findings affected by the above (DATA-001, DATA-006, DATA-009 new, DATA-005 Item D new, SECURITY-002, CONSULTANT-EDGE-001, ASSET-EDGE-001 cross-reference, TIMESHEET-EDGE-001, TIMESHEET-EDGE-007 new, INTEGRATION-002) and their rollups in `testing/README.md`/`testing/TODO.md`; corrected a pre-existing inconsistency in `testing/TODO.md` where DATA-001 was checked as fixed despite its own `Status` field reading "Open." Updated `fixes/DATA-001.md` and `fixes/TODO.md` accordingly. Corrected stale "`asset_approver` identical to `consultant`" wording in `workflow/application-overview.md` and `workflow/data-flow.md`.
- **Same-day correction:** the initial DATA-001 sync (above) incorrectly concluded the raw change was "3 of 4 balance-read sites fixed" — re-derivation with concrete numbers showed the `Type_field != "Reject"` filter added to those three sites actually excludes the *correction* row (the new offsetting insert), not the original deduction, so those three sites are still wrong; only the unfiltered fourth site (the `Leave_Balance` page) is correct. Corrected `testing/data-integrity/balance-ledger-integrity.md`, `testing/integrations/cliq-and-email-notifications.md` (INTEGRATION-002), `testing/TODO.md`, `testing/README.md`, `fixes/DATA-001.md`, `fixes/TODO.md`, `workflow/application-overview.md`, `workflow/data-flow.md`, `workflow/diagrams/leave-request-flow.md`, `workflow/form-workflows/Leave_Request.md`, `code modules/forms/Leave_Balance_Record.md`, `code modules/workflows/Leave_Request-workflows.md`, and `code modules/functions/deluge/notification-functions.md` to state plainly that DATA-001 remains fully open and to recommend removing the filter from the three sites (rather than adding it to the fourth) as the actual fix.
- **Expanded `fixes/` scope, per user instruction:** created a `fixes/<TEST-ID>.md` file for every one of the 51 findings in `testing/` (49 new, in addition to the pre-existing `DATA-001.md`/`DATA-002.md`), not just findings actively being resolved — a deliberate change from the folder's original scope (documented in the updated `fixes/README.md`). Most are `Proposed`: a written fix approach with nothing changed yet. Findings needing a business-owner decision or runtime verification before a concrete fix can be proposed say so explicitly rather than inventing one (e.g. `SECURITY-002.md`, `SECURITY-003.md`, `DATA-008.md`, `CONCURRENCY-002/003.md`, `INTEGRATION-004/005.md`); accepted-as-design and test-planning findings (`SECURITY-004.md`, `REGRESSION-002.md`) say "no fix proposed" outright. Also refreshed stale pre-regenerate `raw/` line citations in `testing/concurrency/race-conditions-and-idempotency.md` (caught by one of the fork batches writing these files) — `testing/integrations/`'s citations didn't need it (no raw line numbers cited there). Updated `fixes/TODO.md`'s rollup to include all 49 new entries, grouped by severity to match `testing/TODO.md`.

### 2026-09-12

- User edited `raw/Omm_Applications.md` directly again and asked to sync `code modules/` and `workflow/` **only** — `testing/` and `fixes/` were explicitly left untouched this round, even where a finding's underlying facts changed. Again done as a full manual re-audit (no git history): four parallel domain passes (Leave; Timekeeping; Assets; Consultant/Client/Admin) plus the coordinator directly re-syncing the cross-cutting Deluge global functions, schedule, connection, and permissions files, all reconciled against the current raw export and each other.
- **Real behavior changes found and synced** (not just line-number churn):
  - `get_balance_html`'s `bal_rec` filter no longer has `&& Type_field != "Reject"` in `raw/` — it now matches what `code modules/` already had as a standalone 2026-09-10 fix, so that divergence between `raw/` and `code modules/` is resolved.
  - `Cliq.Send_Leave_Rejected_Notification`'s balance-reversal logic changed again: the offsetting `Leave_Balance_Record` insert is now tagged `Type_field="Deduct"` (was `"Reject"`), filtered from the original row by `&& Type_field == "Deduct"` (previously unfiltered and redundantly double-assigned). Net effect on the three previously-affected read sites (`get_balance_html`, `Leave_Request.Valid`, `pre_fil_few_fields`'s inline table) is that they're unfiltered again and no longer exclude the offsetting row on `Type_field` grounds — but `Leave_Request`'s own `Success` on-success workflow does an unfiltered upsert against the request's `Leave_Balance_Record` rows, and since the offsetting row now shares the `"Deduct"` tag with the original, `Success` can match and overwrite both together in the same execution. This is a new, distinct interaction from the one logged in DATA-001 on 2026-09-10; whether it changes DATA-001's status is left for `testing/`/`fixes/` to assess, per this round's instruction to leave those alone. `Leave_Balance_Record.Type_field`'s displayname reverted from `"Reject"` back to `"Type"`; `"Reject"` remains a listed picklist choice but no code path writes or filters on it anymore.
  - `Cliq.Send_Leave_Applied_Notification` gained a new early-return condition: `|| mail_notification_rec.Emails.toString() == ""` (previously only checked `recdata.count() == 0`).
  - `share_settings`: the `Write` profile's `ModulePermissions` now cover all 12 forms (previously only 8 were documented — `Asset_Return_Form`, `Asset_Return_Inspection_Form`, `Notification_Mail_Master`, `Role_Master` were missing from the prior doc). More significantly, the portal `consultant` profile's asset permissions were **narrowed**: lost `Viewall`/`ReportPermissions` on `Asset_Return_Form` and `Add_Asset` (down to bare `Create,Tab`), and lost all module access to `Asset_Return_Inspection_Form` (no `enabled` key at all) — while `asset_approver` retained full `Create,Viewall,Tab`+`ReportPermissions` on all three, widening the `consultant`/`asset_approver` gap from one form (logged 2026-09-10) to three. Relevant to SECURITY-002, not updated there per this round's scope.
  - `Asset_Management` report lost its `Consultant_Name.ID == thisapp.F.UF()` row filter entirely — it's now `show all rows`, unlike its siblings (`Timekeeping`, `Leave_Requests`, `Asset_Return_Inspection_Form_Report`) which still carry the filter.
  - `Timekeeping1` gained a new on-validate rule `Duplicate_Submission_Hand` (blocks a save whose `Start_Time`–`End_Time` overlaps another non-`Cancelled` entry for the same consultant + work date). `P2_Hours_Worked_End_Time`'s future-clamp threshold tightened from `now+1h` to `now+15min` and gained a new `Hours_Worked > 24` cap. `Load` now re-anchors `Start_Time`/`End_Time` onto `Work_Date` on every load (previously only when empty). Both `Leave_Request.Save_as` and `Timekeeping1.Save_as` picklists changed from `{"Draft","Submitted"}` to `{"Draft","Ready to Submit"}`; `Save_As`/`Save_As1` were updated to match, but `Timekeeping1`'s `adding_submitted_field_on`/`success1` still gate on the now-UI-unreachable literal `"Submitted"` (only a record function like `Submit`, which writes that value directly, still reaches that branch) — a new latent inconsistency, not logged as a finding per this round's scope.
  - All three asset forms (`Add_Asset`, `Asset_Return_Form`, `Asset_Return_Inspection_Form`) gained new `on validate` rules enforcing conditionally-required fields (sub-reason/ticket, per-accessory condition+image+text, damage description/images) that were previously only implied by show/hide logic. `Reciept_ID` prefixes were reshuffled to be distinct per form: `Add_Asset` = `OMM-ASSET_REP/NEW-` (unchanged), `Asset_Return_Form` = `OMM-ASSET_RET-` (was `OMM-ASSET_REP/NEW-` as of the 2026-09-10 sync — DATA-009's premise no longer holds as stated), `Asset_Return_Inspection_Form` = `OMM-ASSET_RET/INS-` (was `OMM-ASSET_RET-`). `Asset_Return_Form.Hiding_few_fields_on_load2`'s `plain2` reference is **no longer dead** — `plain2` is now a real field on the form (DATA-005 Item D's premise no longer holds as stated).
  - `Asset_Return_Inspection_Form`: the `Consultant_Name` auto-fill rule (`Section_A_Consultant_Name1`) is now `status = inactive` (a `Date_Signed` auto-fill/`must have` rule takes its place); Sections D/E are no longer hidden pending an inspector round-trip (`hide` lines commented out); the "Sign & Verify Return" email link is now dead code (`verify_link`/`sign_button_block` commented out, never reach `email_body`).
  - `Add_Consultant` gained a new `on validate` rule `Validation_on_DOB_DOJ` (blocks add/edit with an alert if both `DOB` and `DOJ` are set and `DOJ < DOB`); `Email`'s `unique` constraint remains in place. `Add_Consultant.Activate_Deactivate`'s `delete`/`deletes` variable-name mismatch is unchanged.
  - `All_Balance_Records` report: `Type_field` column uses an explicit `as "Type"` alias and carries a previously-undocumented `sort by Consultant_Name ascending` clause.
- Per this round's instruction, **`testing/` and `fixes/` were not touched** even though several of the above changes bear directly on existing findings (DATA-001, DATA-009, DATA-005 Item D, SECURITY-002, TIMESHEET-EDGE-001/007) — those files still reflect the 2026-09-10 state and need a follow-up pass before they can be trusted as current.

### 2026-09-15

- User requested a feature/design change to the Timekeeping approval workflow (not a `testing/` finding remediation): (1) remove the inline **"Reject"** action from `Timekeeping_Approval_Report`, and (2) let the admin edit approval-side fields on an already-`Submitted` record. Clarified scope with the user via AskUserQuestion before making changes: apply **only to `code modules/`/`workflow/`, not `raw/`**; remove only the "Reject" *button*, leaving the `Reject` record function and `Load`'s `help=="reject"` branch in place, unreferenced (deliberately orphaned, not deleted); and scope the new edit capability to the approval fields only (`Approver_Comments`/`Reject_Comments`), not a full-record edit.
- Implemented as a clearly-flagged **proposed change, not yet applied to `raw/`**, across: [`code modules/reports/Timekeeping_Approval_Report.md`](code%20modules/reports/Timekeeping_Approval_Report.md) ("Reject" column/action removed; new "Edit Approval Fields" action added, condition `Status == "Submitted"`), [`code modules/functions/record-functions/Timekeeping1-actions.md`](code%20modules/functions/record-functions/Timekeeping1-actions.md) (`Reject` marked orphaned; new `Edit_Approval_Fields` record function added, opens a popup with `help=edit_approval`), [`code modules/workflows/Timekeeping1-workflows.md`](code%20modules/workflows/Timekeeping1-workflows.md) (`Load` gains a new `help == "edit_approval"` branch: shows `Approval` section, hides `Entry_Details`/`Time_Hours`, but does not touch `Status`/`Approver` or queue a notification), [`code modules/forms/Timekeeping1.md`](code%20modules/forms/Timekeeping1.md), [`workflow/form-workflows/Timekeeping1.md`](workflow/form-workflows/Timekeeping1.md), and the approve/reject branch of [`workflow/diagrams/timekeeping-flow.md`](workflow/diagrams/timekeeping-flow.md) (added earlier this session as a new full-process flowchart alongside the existing state-lifecycle diagram).
- No changes made to `raw/Omm_Applications.md`, and no `testing/`/`fixes/` files touched (this was a design/dev request, not a QA finding) — every edited file explicitly notes the divergence from current `raw/` state pending the user's decision to apply it there.

**Same-day follow-up:** user gave a second instruction referencing "the edit button" and asking that it "re-enable the approve button and reject button." Clarified via AskUserQuestion (ambiguous whether "reject button" meant restoring the just-removed action, which "edit" was meant, and what "re-enable" required) — answers: restore Reject; the standard Creator default "Edit" action (not the new `Edit_Approval_Fields` popup); and "re-enable" means guaranteeing `Status` stays/returns to `"Submitted"` after that edit. Applied, still proposed/`code modules/`-only:
- **Reverted** the "Reject" removal from the same day's earlier change — `Timekeeping_Approval_Report`'s inline "Reject" action, and `Reject`/`Load`'s `help=="reject"` branch, are back to matching `raw/` exactly (nothing about Reject is proposed-changed any more).
- **Added** to `Load` (proposed, not in `raw/`): `orig_status = input.Status` captured at the top of the rule, and a new final `else` branch (when `help` matches none of `approval`/`reject`/`edit_approval` — i.e. Creator's built-in default "Edit" action) that re-asserts `input.Status = orig_status`. This guarantees a plain Edit + Save on a `Submitted` record can't leave `Status` at anything else, so `Reject`/`Approve`/`Approve with Comments`/`Edit Approval Fields` (all conditioned on `Status == "Submitted"`) stay available on `Timekeeping_Approval_Report` afterward.
- Updated the same files as the initial change to match: [`Timekeeping_Approval_Report.md`](code%20modules/reports/Timekeeping_Approval_Report.md), [`Timekeeping1-actions.md`](code%20modules/functions/record-functions/Timekeeping1-actions.md), [`Timekeeping1-workflows.md`](code%20modules/workflows/Timekeeping1-workflows.md), [`Timekeeping1.md` (form)](code%20modules/forms/Timekeeping1.md), [`Timekeeping1.md` (form-workflow summary)](workflow/form-workflows/Timekeeping1.md), and [`diagrams/timekeeping-flow.md`](workflow/diagrams/timekeeping-flow.md).

**Second same-day follow-up:** user pointed out the `edit_approval` `Load` branch didn't need to `show Approval`/`hide Entry_Details`/`hide Time_Hours` — the actual requirement was only to keep the Approve button enabled (its report condition is `Status == "Submitted"`). Simplified accordingly, still proposed/`code modules/`-only: the `edit_approval` branch now does nothing but `input.Status = orig_status;`, identical in effect to the default-edit `else` branch added in the first follow-up (kept as two separate branches only for UI-entry-point traceability — "Edit Approval Fields" button vs. Creator's built-in Edit). Updated the same set of files to drop every reference to the branch showing/hiding sections.

**Third same-day follow-up:** user asked why the button needs to open the form at all if the only job is re-enabling the Approve button — "rest of the things approve button will handle." Design converged fully: [`Edit_Approval_Fields`](code%20modules/functions/record-functions/Timekeeping1-actions.md) is now a plain inline `on click` action — `input.Status = "Submitted";` — with **no** `openUrl`, no popup, no `help` param, and no `Load` involvement, mirroring `Approve_Timesheet`'s direct-write pattern instead of `Reject`'s popup-redirect pattern. Removed the now-unused `help == "edit_approval"` branch from `Load` entirely — `Load`'s only remaining proposed change is the unrelated default-edit `else` guarantee (for Creator's separate built-in "Edit" action) from the first follow-up. Flagged in `Timekeeping1-actions.md` that the action's display name "Edit Approval Fields" no longer matches its behavior (nothing is edited/opened any more); not renamed since the user hasn't asked for that yet. Updated the same set of files (`Timekeeping1-workflows.md`, `Timekeeping1-actions.md`, `Timekeeping_Approval_Report.md`, `Timekeeping1.md` form, `Timekeeping1.md` form-workflow summary, `diagrams/timekeeping-flow.md`) to match.

**New feature request, same day:** user asked for a Leave/Timekeeping conflict check — if a consultant has already applied for leave on a `Timekeeping1` entry's `Work_Date`, the entry should auto-fill accordingly and, for a full day off, submission should be blocked. Clarified three business decisions via AskUserQuestion before implementing (none inferable from `raw/`, since this is new functionality): (1) only `Status == "Approved"` leave counts, not `Draft`/`Submitted`; (2) a half-day leave (`Half_Day == "Yes"`) still auto-fills `Leave_Type` as a hint but does **not** block submission — only a full-day leave does; (3) the block happens on validate (`cancel submit`, same pattern as `Duplicate_Submission_Hand`), stopping the save outright rather than just gating the Submit step. Implemented as proposed, `code modules/`-only (not applied to `raw/`), continuing this session's established scope for the Timekeeping approval work:
- `Load` and `Work_Day` (on user input of `Work_Date`) both gained a `Leave_Request[Consultant_Name == ... && Status == "Approved" && From_Date <= Work_Date <= To_Date]` lookup that auto-fills `Timekeeping1.Leave_Type`; `Work_Day`'s copy additionally clears `Leave_Type` when the newly-picked date has no match, since it (unlike `Load`) can re-run repeatedly within one form session.
- New on-validate rule `Leave_Conflict_Check` (same `cancel submit` + `alert` pattern as `Duplicate_Submission_Hand`, running independently alongside it) blocks the save if the same lookup, filtered to `Half_Day == "No"`, finds a match.
- Updated [`Timekeeping1-workflows.md`](code%20modules/workflows/Timekeeping1-workflows.md) (`Load`, `Work_Day`, new `Leave_Conflict_Check` section), [`Timekeeping1.md` (form)](code%20modules/forms/Timekeeping1.md) (field note, attached workflows, new `Leave_Request` read dependency), [`Leave_Request.md`](code%20modules/forms/Leave_Request.md) (cross-reference back to the new reader), [`Timekeeping1.md` (form-workflow summary)](workflow/form-workflows/Timekeeping1.md) (table rows + new "Proposed change #2" section), and [`diagrams/timekeeping-flow.md`](workflow/diagrams/timekeeping-flow.md) (new nodes in the Entry/Details/Submission subgraphs of the full-process flowchart, plus an explanatory note).
- Noted but not resolved (flagged in `Timekeeping1-workflows.md`, not filed as a `testing/` finding since this is proposed/not-yet-real functionality): the check only affects new saves going forward — it doesn't retroactively flag an already-`Submitted`/`Approved` `Timekeeping1` entry for a date that later gets an approved leave.

**Bug report, same day, on `Leave_Request` (unrelated to the Timekeeping work above):** user reported that toggling `Half_Day` back to `"No"` leaves `Number_of_Days` stuck at `0.5` instead of recalculating. Verified directly against `raw/Omm_Applications.md:5175-5210` (`enabling_half_day_session`) — confirmed real, present in `raw/` today: the `else` branch (`Half_Day == "No"`) only runs `hide Half_Day_Session;`, never recomputing `Number_of_Days` the way `P1_cal_no_of_days_from`/`P2_cal_no_of_days_to` do. Unlike the Timekeeping items above (net-new proposed functionality), this is a genuine existing defect, so it went through the full `testing/`+`fixes/` pipeline rather than being fixed ad hoc:
- Logged as **LEAVE-EDGE-008** (DEFECT, MEDIUM) in [`testing/edge-cases/leave/leave-validation-and-balance.md`](testing/edge-cases/leave/leave-validation-and-balance.md), cross-referenced against the related-but-opposite-direction LEAVE-EDGE-002 (dates edited after Half Day leaves `Half_Day` stuck "Yes" with a stale count; LEAVE-EDGE-008 is `Half_Day` correctly reset but `Number_of_Days` left stale).
- Wrote [`fixes/LEAVE-EDGE-008.md`](fixes/LEAVE-EDGE-008.md) with the exact before/after Deluge and applied the fix to `code modules/workflows/Leave_Request-workflows.md`'s `enabling_half_day_session` (status: **Applied to code modules/**, not `raw/` — mirrors this session's "propose here first" pattern, though this fix file's status lifecycle is the standing `fixes/` one, not a special case).
- Updated `testing/TODO.md` (new entry + finding count 51→52), `testing/README.md` (index row), `fixes/TODO.md` (new entry), and [`code modules/forms/Leave_Request.md`](code%20modules/forms/Leave_Request.md) (attached-workflow note) to match.
- Not applied to `raw/Omm_Applications.md` — awaiting the user's explicit go-ahead, same as every other `raw/` change this session.

**Follow-up on the Leave/Timekeeping conflict feature, same day:** user reported "Start Time cannot be in the future." and "End Time cannot be earlier than Start Time." firing unexpectedly. Confirmed via AskUserQuestion that the trigger is: a consultant with an Approved half-day leave opens a new `Timekeeping1` entry early in the day to pre-fill their planned hours, and `Load`'s default 9:00 AM–6:30 PM window is still in the future relative to the actual clock, so `P1_Hours_Worked_Start_Tim`/`P2_Hours_Worked_End_Time`'s future-time clamps fire even though nothing is actually wrong — and confirmed the desired fix is to relax those specific clamps on a half-day-leave date (not remove the future-time guard generally). Extended `P1`/`P2` in [`Timekeeping1-workflows.md`](code%20modules/workflows/Timekeeping1-workflows.md) with the same `Leave_Request` lookup pattern as `Leave_Conflict_Check`, filtered to `Half_Day == "Yes"`, and skip the clamp when it matches — the chronological-order check and `Hours_Worked > 24` cap are untouched. As a documented side effect, this also closes the half-day-leave case of the pre-existing "clamp swallows the order-check" edge case noted in `P2`'s own doc (unrelated non-leave dates still have that edge case). Updated [`Timekeeping1.md` (form)](code%20modules/forms/Timekeeping1.md), [`Timekeeping1.md` (form-workflow summary)](workflow/form-workflows/Timekeeping1.md), and [`diagrams/timekeeping-flow.md`](workflow/diagrams/timekeeping-flow.md) to match. Proposed/`code modules/`-only, continuing this session's scope — not applied to `raw/`. Not filed as a separate `testing/`/`fixes/` finding, since it's a refinement of this session's own not-yet-real proposed feature rather than an independent defect in the current live app.

**Second follow-up on the Leave/Timekeeping conflict feature, same day:** user pointed out that applying for leave *today* and then filling in *today's* `Timekeeping1` entry is exactly the case where the `Load`/`Work_Day` autofill fails — `Work_Date` defaults to `${zoho.currentdate}`, so it's already correct and never actually "changes," meaning `Work_Day`'s on-user-input trigger (the only thing that re-runs the leave lookup after the initial page load) never fires, so a leave approved after `Load` already ran is silently missed. Fixed by moving the authoritative check into [`Leave_Conflict_Check`](code%20modules/workflows/Timekeeping1-workflows.md#leave_conflict_check-proposed) (on validate): it now unconditionally re-runs the `Leave_Request` lookup and re-assigns `Leave_Type` immediately before every save, replacing its earlier `Half_Day == "No"`-only query — this is the one point in the form's lifecycle guaranteed to run regardless of which fields the user touched (Creator runs on-validate on every add/edit submit, Draft or Ready to Submit alike). `Load`/`Work_Day`'s autofill is downgraded to a best-effort early UI hint; it no longer determines what's actually saved. Updated [`Timekeeping1.md` (form)](code%20modules/forms/Timekeeping1.md), [`Timekeeping1.md` (form-workflow summary)](workflow/form-workflows/Timekeeping1.md), and [`diagrams/timekeeping-flow.md`](workflow/diagrams/timekeeping-flow.md) to match. Proposed/`code modules/`-only, same scope as the rest of this feature — not applied to `raw/`.

**Third follow-up on the Leave/Timekeeping conflict feature, same day:** user asked how a consultant should actually fill in `Timekeeping1` on a half-day-leave date — whether `Half_Day_Session` ("First Half"/"Second Half") could drive default `Start_Time`/`End_Time`. Clarified three points via AskUserQuestion: (1) `Half_Day_Session` names the half the consultant is **off**, so the default working window should be the *opposite* half; (2) the midpoint splitting the two halves must be computed **dynamically** from whatever the record's actual baseline `Start_Time`/`End_Time` are — not a fixed clock time — since different consultants' actual hours differ (the user's own example: "what if time starts at 8:30"); the user also asked for the same kind of informational alert `Leave_Conflict_Check` already shows for a full-day leave, but non-blocking, for half-day; (3) the narrowed default should stay fully editable. Implemented in [`Timekeeping1-workflows.md`](code%20modules/workflows/Timekeeping1-workflows.md): `Load` now captures whether `Start_Time`/`End_Time` were both null before its existing defaulting block runs, and — only for that genuinely-fresh-entry case, so a re-opened Draft's own edits are never clobbered — computes the midpoint from whatever the defaulting block just produced and narrows to the working half (`"First Half"` off → `Start_Time` moves to the midpoint, working the back half; `"Second Half"` off → `End_Time` moves to the midpoint, working the front half); an informational `alert` (not `cancel submit` — this is `on load`, where that's invalid anyway) fires every time a half-day leave matches, narrowing or not. `Work_Day` gets the same alert (no narrowing, since a `Work_Date` change already resets both times to midnight — a zero-width window). Updated [`Timekeeping1.md` (form)](code%20modules/forms/Timekeeping1.md), [`Timekeeping1.md` (form-workflow summary)](workflow/form-workflows/Timekeeping1.md), and [`diagrams/timekeeping-flow.md`](workflow/diagrams/timekeeping-flow.md) to match. Proposed/`code modules/`-only, same scope as the rest of this feature — not applied to `raw/`.

### 2026-09-16

- User pasted a new `raw/Omm_Applications.md` (generated 16-Sep-2026 09:39:20, ~11,430 lines — a substantially fuller export than the 2026-09-12 version) and asked to cross-verify every remaining folder against it and update what's necessary. Per [[Never touch/offer to update raw/]], this sync touched only `code modules/`/`workflow/` — `raw/` was never modified. Done as five parallel domain passes (Assets; Leave; Timekeeping; Consultant/Client/Admin/permissions/connections; cross-cutting Deluge helper/notification functions + schedule), each independently re-reading its slice of raw in full and reconciling against current `code modules/`/`workflow/` content. `testing/`/`fixes/` reconciliation is a separate follow-on pass (not part of this entry — see below).
- **Headline finding:** raw/ now independently contains real implementations that substantially overlap with two features this session had previously built as *proposed, code-modules-only* (2026-09-15, not yet in raw): (1) the Leave/Timekeeping conflict check — raw's mechanism differs from what was proposed (a new `Error_Tagging` picklist field flags a full-day-leave match, consumed by a second `on validate` actions block bolted onto `Duplicate_Submission_Hand`, rather than a standalone `Leave_Conflict_Check` rule; raw's version does not refresh `Leave_Type` at validate time the way the proposed one does); (2) the half-day-leave future-clamp exemption in `P1_Hours_Worked_Start_Tim`/`P2_Hours_Worked_End_Time` — byte-identical mechanism to what was proposed. Still confirmed absent from raw: the `orig_status` default-edit Status guarantee, the half-day window-narrowing/midpoint-alert logic in `Load`/`Work_Day`, and the proposed `Edit_Approval_Fields` action (raw does have a distinct real function, lowercase `edit_approval`, condition `Status=="Approved"`, that reverts an approved timesheet back to Submitted — different purpose, kept as a separate documented component). All six proposed items remain clearly flagged as proposed/not-in-raw in `code modules/`; the three now-real overlapping mechanisms are documented separately, cross-referenced, not merged into the proposed docs without user direction.
- **DATA-001 mechanism now appears resolved in raw itself**, not just as a `code modules/`-side proposal: `Cliq.Send_Leave_Rejected_Notification`'s offsetting `Leave_Balance_Record` insert is tagged `Type_field="Reject"` again (reverted from the transient 2026-09-12 `"Deduct"` tag); all four balance-read sites (`get_balance_html`, `Leave_Request.Valid`, `pre_fil_few_fields`'s inline table, the portal `Leave_Balance` page) now sum unfiltered by `Type_field`; and `Leave_Request.Success`'s on-success upsert (scoped to `Type_field=="Deduct"`) can no longer collide with the `"Reject"`-tagged offsetting row. Net effect: a rejection nets to zero in raw/ itself now. This needs formal re-verification and a status update in `testing/data-integrity/balance-ledger-integrity.md` and `fixes/DATA-001.md` (not done in this entry — flagged for the follow-on `testing/`/`fixes/` pass).
- **LEAVE-EDGE-008's fix has landed in raw itself** — `enabling_half_day_session`'s `Half_Day == "No"` branch now recomputes `Number_of_Days`, byte-identical to the fix `code modules/` proposed on 2026-09-15 (plus one extra raw comment). Needs a status update in `fixes/LEAVE-EDGE-008.md` (not done in this entry).
- **Other real changes found and synced** (not exhaustive — see each domain's files for full detail):
  - `Leave_Request.Valid`'s guard changed from the permanent `if(input.Balance_Deducted = false)` lock to `if(input.help != "approval")` — the balance/half-day check now re-runs on every non-approval save rather than being permanently disabled once triggered once. `Balance_Deducted` is still set by `Approve1` but now read nowhere (dead/vestigial field) — CONCURRENCY-005's documented root cause no longer applies as stated; needs reassessment. A new wrinkle: the reject-popup save path is no longer exempted from the balance check either.
  - `Leave_Request` gained 3 previously-undocumented plaintext spacer fields (`plain`/`plain1`/`plain2`).
  - `Add_Consultant`: `Current_Address`, `DOJ`, and `Bank_Account_Number` lost their `must have` (required) status — may affect any existing edge-case findings that assumed those fields were guaranteed non-null.
  - `Timekeeping1`: new field `Error_Tagging` (picklist, `{"Half Day Leave Error"}` — name is misleading, it's actually set for a *full-day* leave match); `P2_Hours_Worked_End_Time`'s future-clamp threshold widened again, `now+15min` → `now+30min`; `Reject` record function is now `status = inactive` in raw and its Cliq dispatch (`task_rejected`) is commented out — the whole Reject flow now looks deliberately disabled even though the report action/condition is still wired up (candidate new finding, not yet filed); `Error_Tagging` is never cleared once set, even if the underlying leave is later cancelled (candidate new finding, not yet filed).
  - `get_balance_html`'s HTML output was restyled (gradient card, zebra-striped rows) — cosmetic only, same query/arithmetic. Six `Cliq.Send_*` notification functions' `purl` construction switched from a hardcoded URL literal to `thisapp.Cliq.cliq_base_url() + channel + "/message"` — same resulting URL, source de-dup only.
  - `asset_approver` vs. `consultant` permission gap on the three asset forms: unchanged from 2026-09-12 (SECURITY-002's premise still holds as documented). Newly noticed, not previously part of SECURITY-002: the two profiles also differ on `Leave_Request` `ReportPermissions` (`{"View"}` vs. `{"View","Edit"}`) — may be worth folding in.
  - Three asset forms' `Consultant_Name` reassignment guard: confirmed still absent (CONSULTANT-EDGE-001 still open there, unchanged from 2026-09-10/12).
  - `Asset_Management` report's row filter: confirmed still absent (removed as of 2026-09-12, unchanged).
- Updated files: `code modules/forms/{Leave_Request,Leave_Balance_Record,Add_Consultant}.md`; `code modules/workflows/{Leave_Request,Timekeeping1}-workflows.md`; `code modules/functions/record-functions/Timekeeping1-actions.md`; `code modules/functions/deluge/{helper-functions,notification-functions}.md`; `code modules/reports/Timekeeping_Approval_Report.md`; `code modules/permissions/profiles.md`; `workflow/form-workflows/{Leave_Request,Add_Consultant,Timekeeping1}.md`; `workflow/diagrams/{leave-request-flow,data-001-flow,timekeeping-flow}.md`; `workflow/function-workflows/notification-dispatch.md` (corrected a stale note that still described the transient 2026-09-12 `"Deduct"` tag as current). `code modules/forms/{Add_Asset,Asset_Return_Form,Asset_Return_Inspection_Form}.md` and their workflows/reports were independently re-verified against this raw and found already accurate (synced by the Assets domain pass). All other files in scope were re-verified with no real changes needed (only source line-number refreshes, not logged individually here).
- `testing/` and `fixes/` were **not** touched in the code modules/workflow sync above — the findings affected by it needed a dedicated reconciliation pass, done as a same-day follow-on (see below).

**Same-day `testing/`/`fixes/` reconciliation:** done as three parallel passes (Leave/balance: DATA-001, LEAVE-EDGE-008, CONCURRENCY-005, INTEGRATION-002; Timekeeping: TIMESHEET-EDGE-001/007 plus new candidates; Permissions/Consultant: SECURITY-002, CONSULTANT-EDGE-001, plus a new candidate), each independently re-deriving conclusions from current `raw/` rather than trusting the sync summary, followed by a coordinator pass resolving three findings whose premises turned out stale as side-discoveries (ASSET-EDGE-001, CONSULTANT-EDGE-003, TIMESHEET-EDGE-004) and filing one further new finding (CONCURRENCY-006). Net result:
- **Fixed/Resolved, confirmed by direct re-derivation against current `raw/` (not applied by Claude — `raw/` converged independently in every case):** DATA-001 (all four balance-read sites now agree and net to zero after a rejection), LEAVE-EDGE-008 (its 2026-09-15 `code modules/`-only fix now matches `raw/` byte-for-byte), CONCURRENCY-005 (original permanent-lock mechanism replaced by a transient `input.help` check — a new, narrower risk in the replacement is noted in place, not filed separately), ASSET-EDGE-001 (the blocking `Consultant_Name` auto-fill rule on `Asset_Return_Inspection_Form` is now `status = inactive`), TIMESHEET-EDGE-004 (a real on-validate overlap check, `Duplicate_Submission_Hand`, now exists).
- **Partially resolved:** INTEGRATION-002 (tactical correctness fixed as a DATA-001 byproduct; the architectural duplication across four implementations is unchanged), CONSULTANT-EDGE-003 (the DOJ-before-DOB half is now covered by `Validation_on_DOB_DOJ`; the future-date half stays open, finding re-scoped accordingly).
- **Re-scoped, still open:** CONSULTANT-EDGE-001 (narrowed from 3 to 2 of 5 forms — `Asset_Return_Inspection_Form` dropped since its mechanism is now inactive), SECURITY-002 (asset-form gap unchanged; a `Leave_Request` `ReportPermissions` asymmetry was investigated and folded in as a non-exposure consistency note rather than a new Test ID, after confirming the direction of the asymmetry was initially assumed backwards).
- **Re-verified unchanged:** TIMESHEET-EDGE-001, TIMESHEET-EDGE-007.
- **New findings filed** (52 → 56 total): **TIMESHEET-EDGE-008** (DEFECT, HIGH — `Timekeeping1`'s Reject is wired up in `Timekeeping_Approval_Report` but the underlying record function is now `status = inactive` and the rejection Cliq notification is separately commented out), **TIMESHEET-EDGE-009** (RISK/EDGE CASE, LOW — the new `Error_Tagging` field's name is inverted from its actual trigger condition and is never cleared, though a normal form save can't currently persist it in a stale state), **CONSULTANT-EDGE-004** (DEFECT, MEDIUM — `Add_Consultant.Current_Address` lost its `must have` status but `Add_Asset.Section_A_address_copy` still assumes it's non-null, producing a disabled-empty-required-field dead end with a workaround), **CONCURRENCY-006** (RISK, MEDIUM — `Send_Leave_Rejected_Notification`'s offsetting-insert guard checks for an existing `Deduct` row rather than an existing `Reject` row, so a retried/duplicate invocation could insert a second offsetting credit — DATA-001's opposite-direction sibling risk).

### 2026-09-17

- User added a new ERD, [`Excalidraw/expense_tracker_erd.excalidraw.md`](Excalidraw/expense_tracker_erd.excalidraw.md), for a new "Expense Tracker" module (`TRIP`, `EXPENSE_REPORT`, `EMPLOYEE_TRAVEL_DOCUMENT`, `EXPENSE_CATEGORY`, `EXPENSE`, plus `EMPLOYEE` shown with no fields of its own), and asked to **back-build Zoho Creator forms from the ERD** rather than extract from `raw/` — this data model does not exist in `raw/Omm_Applications.md` at all. Confirmed two structural decisions with the user via AskUserQuestion before building: (1) `EMPLOYEE` in the ERD is the existing `Add_Consultant` form reused, not a new module; (2) the new forms live in a **new top-level `Expense/` folder** (sibling to `raw/`, `code modules/`, `workflow/`, `testing/`, `fixes/`), flat — not mirroring the `code modules/forms/` + `workflow/` split, and not nested under `code modules/forms/`.
- Built the first form, [`Expense/Expense_Category.md`](Expense/Expense_Category.md) (`ID`/`Category_Name`/`Category_Code`(unique)/`Description`/`Is_Active`, ERD's `Created_By`/`Created_Time`/`Modified_Time` mapped to Creator's built-in system columns rather than custom fields, matching how every existing form in this app already handles them), clearly flagged as **proposed, not in `raw/`**. Left validation logic, permissions, and a report module as explicit open questions rather than inventing them — the ERD specifies data shape, not behavior.
- Built the second form, [`Expense/Expense.md`](Expense/Expense.md): `Expense_Date`/`Merchant`/`Category` (lookup → `Expense_Category.ID`)/`Amount`/`Currency`/`Is_Reimbursable`/`Description`/`Reference_Number`/`Receipt`/`Status`/`Rejection_Reason`. `Status`'s `Draft`/`Submitted`/`Approved`/`Rejected` values are inferred (the ERD lists the bare field, not its values) from the same pattern used by `Leave_Request.Status`/`Timekeeping1.Status`. `Receipt` modeled as Creator's generic File Upload type rather than `image` (existing asset-photo fields all use `image`, but a receipt is often a PDF/forwarded e-receipt). Flagged open questions: whether `Expense.Status` is really independent of its parent `Expense_Report`'s status (partial per-line rejection) or should just mirror it, whether `Expense` is ever created outside the `Expense_Report` subform context per the ERD's `contains (subform)` relationship, and `Currency` as free text vs. a fixed list. `TRIP`, `EXPENSE_REPORT`, and `EMPLOYEE_TRAVEL_DOCUMENT` remain unbuilt.
- This is a deliberate departure from this file's own defined Folder Structure (which describes `code modules/`/`workflow/` as the managed representation of the `raw/`-sourced application) — done at explicit user direction for a module that has no `raw/` counterpart yet, same pattern as the 2026-09-15 proposed Timekeeping features but scoped to its own top-level folder instead of living inside `code modules/`. `raw/` was not touched.
- Wrote `fixes/CONCURRENCY-006.md` (new) and updated `fixes/DATA-001.md`, `fixes/LEAVE-EDGE-008.md`, `fixes/CONCURRENCY-005.md`, `fixes/INTEGRATION-002.md`, `fixes/ASSET-EDGE-001.md`, `fixes/CONSULTANT-EDGE-003.md`, `fixes/TIMESHEET-EDGE-004.md`, plus new `fixes/TIMESHEET-EDGE-008.md`, `fixes/TIMESHEET-EDGE-009.md`, `fixes/CONSULTANT-EDGE-004.md` (all `Proposed` except where noted above). Synced `testing/TODO.md` (progress line corrected to top-level-finding granularity: 17/56, noting sub-item-scenario granularity separately as 21/68), `testing/README.md`'s index, and `fixes/TODO.md` to match all of the above.

### 2026-09-23

- User updated `raw/Omm_Applications.md` (generated 23-Sep-2026 06:28:53, 15,300 lines, up from ~11,430) and asked to sync `code modules/`. Synced `code modules/` and `workflow/`; **`testing/` and `fixes/` were not touched**, even where findings are affected (listed below). `raw/` was not modified. Done as a full re-audit: every form's fields, every workflow rule, record function, global function, report, schedule, permission and connection was compared against the new export with scripts (field/property diff, whitespace- and comment-insensitive script diff, report column/action diff), then updated.
- **Leave: Days/Hours tracking.** This is the feature built with the user earlier in this session, now in `raw/`. New field `Leave_Request.Leave` ("Leave Tracking", Days/Hours) and two subform forms, `Leave_Request_Subform` (`Leave1`: date + Full/Half/Quarter Day + sub-types) and `Leave_Request_Subform_Hours` (`Leave_Hours`: start/end datetime). `Half_Day`/`Half_Day_Session` and `enabling_half_day_session` were removed. `P1`/`P2` rewritten; new rules `switching_between_hours_a`, `Displaing_the_sub_type_ba`, `increasing_the_count_on_s`, `Increasing_the_count_on_E`; new global function `buildDateRange`. `Number_of_Days` (now labelled "Total") is recalculated from the rows. New record functions `editing_after_approval_or` ("Re-Edit") and `Cancel3`. Observed and documented, not logged in `testing/`: hours stored in a days field and deducted as days; `Success` now forces `Status = "Submitted"` on every save; both subforms hidden on reopen; the End Time rule clears the start time; `Cancel3` writes `"Cancel"`; `Save_as` hidden, so the leave-applied notification doesn't queue. The validation rule drafted this session is not in `raw/`.
- **Timekeeping.** `Duplicate_Submission_Hand` rewritten (the script drafted this session): one entry per consultant per day, and leave blocking via the new `Leave1`/`Leave_Hours` rows; the `Error_Tagging` mechanism is gone. `Load`/`Work_Day` leave lookups lost their `Status == "Approved"` filter; `P1`/`P2` clamp exemptions now cover any Approved leave. `success1` now always sets `Status = "Submitted"` and `Submitted_On`. New field `Supporting_Timezone` (shown for Oracle-client consultants); `Edit_Record1` fixed (now opens `Timekeeping1`/`Timekeeping`). New daily schedule `Timesheet_Reporting` + `Cliq.Send_Timesheet_Approval_Reminder`; new form `Timesheet_Approval_Filter` with its two new pages (`Timekeeping_Page`, `Timekeeping_Approval_Page`). The 2026-09-15 proposals that depended on `Half_Day` are marked obsolete in `Timekeeping1-workflows.md`.
- **Assets.** Four accessory Yes/No fields became `must have`; 12 new `Img_*` photo-type rules use new global function `isValidImage` and new form `validation_errors` (every second invalid upload bypasses the check). `Add_Asset`'s email now matches the ASSET-EDGE-004 fix in `raw/`; `Asset_Return_Form` still attaches `Upload_Images1` twice; `Asset_Return_Inspection_Form` attaches multi-image fields directly.
- **Expense module (new in `raw/`).** Forms `Expense_Report`, `Expense_Subform`, `Expense_Category`, `Trip_Report`, with workflows, the `swapping_is_active` record function and four reports, documented under `code modules/`. They differ from the ERD-based drafts in the top-level `Expense/` folder; those drafts now carry a "superseded" banner pointing to the new docs. Observed: no approval flow, placeholder picklists, wrong subtotal on row delete (`xx`), debug alert on submit, no non-admin permissions.
- **Other:** `Add_Consultant.Phone_Number`/`Local_Duty_Time_Zone` no longer required; `get_balance_html` rounds its figures; empty `F.sdfgh` added; `Leave_Approval_Requests` lost its Client Name column and gained "Re-Edit"; `Timekeeping` report dropped `Billable`; `Timekeeping_Approval_Report` gained `ID`; `Write`/`consultant` gained the timesheet filter/page permissions. Connection, roles, `Add_Balance`, all six existing `Cliq.Send_*` functions, and the Add_Client/Add_Timezone/Leave_Master/Leave_Balance_Record/Role_Master/Notification_Mail_Master forms are unchanged.
- New files: `code modules/forms/{Leave_Request_Subform,Leave_Request_Subform_Hours,Expense_Category,Expense_Report,Expense_Subform,Trip_Report,validation_errors,Timesheet_Approval_Filter}.md`; `code modules/workflows/{Expense_Category,Expense_Report,Timesheet_Approval_Filter}-workflows.md`; `code modules/functions/record-functions/Expense_Category-actions.md`; `code modules/schedules/Timesheet_Reporting.md`; eight new report docs; `workflow/form-workflows/{Expense_Report,Expense_Category,Timesheet_Approval_Filter}.md`. Rewritten: the Leave_Request and Timekeeping1 form/workflow/action docs, `workflow/application-overview.md`, `workflow/data-flow.md`, `workflow/diagrams/{application-overview,leave-request-flow,timekeeping-flow}.md`; `data-model-erd.md` gained the 8 new forms. Source line citations were refreshed across all `code modules/` docs, and 32 stale intra-doc anchors were repaired.
- **Needs a `testing/`/`fixes/` pass:** ASSET-EDGE-004 (now fixed for `Add_Asset` only), the `Edit_Record1` stale-link finding (fixed), TIMESHEET-EDGE-004/007/009 and CONCURRENCY-005 (mechanisms changed), SECURITY-002 (unchanged), and the new observations above.

### 2026-09-24

- User requested a new "comp off" (compensatory time off) mechanism. Confirmed via `AskUserQuestion` (twice — first the overall design, then a correction once the stated premise didn't hold) that this is genuinely new business logic: a full-text search of `raw/Omm_Applications.md` (2026-09-23 export) for weekend/holiday/overtime/comp-off terms found nothing except `Leave_Master`'s unrelated `{"Holiday","Vacation","Sick"}` picklist — there was no existing field "ready" on `Timekeeping1` for this as the user first assumed. Once clarified, the design settled on reusing `Timekeeping1`'s existing `Leave_Type` picklist as the earning trigger (set to a new "Comp Off" `Leave_Master` record), crediting 1:1 from `Hours_Worked` at Timekeeping approval time, and reusing the existing `Leave_Request`/`Leave_Balance_Record`/`get_balance_html` machinery for spending with no new code needed there.
- Implemented as a **proposed change, `code modules/` only, not applied to `raw/`** — same pattern as every other new-functionality change this session (2026-09-15's Timekeeping approval work, 2026-09-17's Expense Tracker). Changes: `Approve` and `Approve_Timesheet` record functions in [`Timekeeping1-actions.md`](code%20modules/functions/record-functions/Timekeeping1-actions.md) now insert a `Leave_Balance_Record` row (`Type_field="Add"`, `Days=Hours_Worked`, no `Leave_Request` link — mirrors the existing `Add_Balance` schedule's accrual rows, so no schema change was needed) and call a new notification function when the approved entry's `Leave_Type` is "Comp Off"; new function `Cliq.Send_CompOff_Credited_Notification` added to [`notification-functions.md`](code%20modules/functions/deluge/notification-functions.md), following the existing `Cliq.Send_Timesheet_*` template, keyed to a new (not-yet-created) `Notification_Mail_Master` row `Type_field="Comp Off Credited"`. Documentation updated to match in [`Timekeeping1.md`](code%20modules/forms/Timekeeping1.md) (form), [`Leave_Master.md`](code%20modules/forms/Leave_Master.md), [`Notification_Mail_Master.md`](code%20modules/forms/Notification_Mail_Master.md), [`Leave_Balance_Record.md`](code%20modules/forms/Leave_Balance_Record.md), [`workflow/form-workflows/Timekeeping1.md`](workflow/form-workflows/Timekeeping1.md), and [`workflow/diagrams/timekeeping-flow.md`](workflow/diagrams/timekeeping-flow.md) (new branch in the `ADMIN` subgraph).
- Flagged, not fixed (new proposed functionality, not an existing defect, so not filed as a `testing/` finding): `edit_approval` can revert an Approved `Timekeeping1` entry back to `Submitted` with no restriction, so a Comp-Off-tagged entry approved twice would be credited twice — the same shape as the existing `CONCURRENCY-006` finding on the Leave side.
- No changes to `raw/Omm_Applications.md`, and `testing/`/`fixes/` not touched (new feature, not a QA finding).

**Same-day follow-up:** user reported two problems after reviewing/testing the above. (1) Crediting `Days = Hours_Worked` 1:1 was wrong — it would credit e.g. `9.5` "days" for one 9.5-hour entry instead of a proper day-equivalent; confirmed via `AskUserQuestion` that comp-off days should be normalized against a **9-hour standard workday (8:00 AM–5:00 PM)**, i.e. `Days = Hours_Worked / 9`. (2) Testing the proposed script in the live Creator editor threw `Variable 'Hours_Worked' is not defined` on the `input.Hours_Worked` reference inside the `insert into [...]` block in both `Approve` and `Approve_Timesheet`; fixed by re-fetching the record (`tk_rec = Timekeeping1[ID == input.ID]`) and reading `Hours_Worked` off that, matching the `recdata = Timekeeping1[ID == rid]` pattern already used by every `Cliq.Send_Timesheet_*` function instead of referencing `input.Hours_Worked` inline. Updated [`Timekeeping1-actions.md`](code%20modules/functions/record-functions/Timekeeping1-actions.md) (both blocks + the design section), [`notification-functions.md`](code%20modules/functions/deluge/notification-functions.md) (`Cliq.Send_CompOff_Credited_Notification` now computes and shows `Days Credited` separately from `Hours Worked`), [`workflow/form-workflows/Timekeeping1.md`](workflow/form-workflows/Timekeeping1.md), and [`workflow/diagrams/timekeeping-flow.md`](workflow/diagrams/timekeeping-flow.md). Still proposed/`code modules/`-only, not applied to `raw/`.

**Second same-day follow-up:** user asked to validate the new mechanism against the rest of the Timekeeping↔Leave_Request sync logic. Found and fixed, still proposed/`code modules/`-only:
- **`Load`/`Work_Day` could silently overwrite or wipe a manual "Comp Off" selection.** `Load`'s leave-autofill has no `Status` filter (any Draft/Rejected/Cancelled leave later appearing for that date would overwrite `Leave_Type` on the next load); `Work_Day` additionally clears `Leave_Type` to `null` on a `Work_Date` edit when the new date has no covering leave. Both rules now skip their autofill/clear entirely once `Leave_Type` is already "Comp Off," confirmed with the user before implementing (trade-off: only a manual dropdown change can move an entry off "Comp Off" afterward).
- **Double-credit risk (previously just flagged) — closed.** New checkbox field `Timekeeping1.Comp_Off_Credited` (initial false), set `true` when `Approve`/`Approve_Timesheet` insert the credit row; the credit block's condition now also requires `Comp_Off_Credited != true`, so re-approving a credited entry after `edit_approval` reverts it no longer double-credits.
- **New gap found and fixed: un-credited-on-cancel.** `Approve` (credits) → `edit_approval` (reverts to Submitted) → `Cancel1` (cancels) previously left the balance credited for a Cancelled entry. `Cancel1` now checks `Comp_Off_Credited` and, if set, inserts an offsetting `Type_field="Deduct"` row (same recompute-and-negate approach as the credit) before cancelling and clearing the flag — same "insert an offsetting row" pattern as `Leave_Request`'s own rejection reversal (`DATA-001`).
- Updated [`Timekeeping1-actions.md`](code%20modules/functions/record-functions/Timekeeping1-actions.md) (`Approve`/`Approve_Timesheet`/`Cancel1` + rewritten design section), [`Timekeeping1-workflows.md`](code%20modules/workflows/Timekeeping1-workflows.md) (`Load`/`Work_Day` guards), [`Timekeeping1.md`](code%20modules/forms/Timekeeping1.md) (form — new field, updated workflow/dependency notes), [`Leave_Balance_Record.md`](code%20modules/forms/Leave_Balance_Record.md), [`workflow/form-workflows/Timekeeping1.md`](workflow/form-workflows/Timekeeping1.md), and [`workflow/diagrams/timekeeping-flow.md`](workflow/diagrams/timekeeping-flow.md) (new guard/reversal nodes in both diagrams). Still proposed/`code modules/`-only, not applied to `raw/`.

**Third same-day follow-up:** user pointed out the new `Comp_Off_Credited` checkbox doesn't exist in the live app ("i have not created comp off button... i want you to work without it") and asked for the mechanism to work without it. Reverted the `Comp_Off_Credited` field and everything gated on it: `Approve`/`Approve_Timesheet` no longer check/set it (back to crediting whenever `Leave_Type == "Comp Off"`, with no re-approval guard), and `Cancel1` is back to its original `input.Status = "Cancelled";` with no reversal logic. The `Load`/`Work_Day` guards protecting a manual "Comp Off" selection from being overwritten (added in the prior follow-up) are unaffected — they don't depend on `Comp_Off_Credited`. The double-credit-on-re-approval and un-credited-on-cancel risks are back to open/documented-not-fixed, explicitly noted as deliberate (no tracking field) rather than an oversight. Updated the same files as the prior follow-up to match: [`Timekeeping1-actions.md`](code%20modules/functions/record-functions/Timekeeping1-actions.md), [`Timekeeping1.md`](code%20modules/forms/Timekeeping1.md), [`Leave_Balance_Record.md`](code%20modules/forms/Leave_Balance_Record.md), [`workflow/form-workflows/Timekeeping1.md`](workflow/form-workflows/Timekeeping1.md), [`workflow/diagrams/timekeeping-flow.md`](workflow/diagrams/timekeeping-flow.md).

**Separately, user asked to validate the sync between `Timekeeping1` and `Leave_Request` on the cancel/reject side too.** Rejection is fine as-is (the existing offsetting-row mechanism is generic by `Leave_Type`, already covers Comp-Off-funded leave). Cancellation is broken: `Leave_Request`'s wired-up "Cancel" action (`Cancel3`) writes `input.Status = "Cancel"` — not the real picklist value `"Cancelled"` — and never reverses the `Leave_Balance_Record` "Deduct" row, so a cancelled request (Comp-Off-funded or not) permanently loses that balance with no way back. This is a pre-existing defect in current `raw/`, not something the Comp Off work introduced, and was already flagged inline in `Leave_Request-actions.md` as "not yet logged in `testing/`." User said they're fixing the `Status` value directly in `raw/` themselves ("i changed it cancelled updates in raw pending") — confirmed via a direct `raw/` read that this hadn't landed in the file yet as of this check; full sync (and closing out the `testing/`/`fixes/` side of this) is pending the user saving that `raw/` update.

**Fourth same-day follow-up — Comp Off 30-day expiry:** user asked whether comp-off balance can expire after 30 days. Since the balance ledger is just a flat running sum (no per-credit tracking anywhere in the app), clarified three design decisions via `AskUserQuestion` before implementing: (1) the 30-day clock starts from the date credited (the `Leave_Balance_Record` "Add" row's `Added_Time`), not the work date; (2) usage is tracked FIFO — oldest credit consumed first — computed statelessly each run rather than mutating a stored remaining-balance field, so only the genuinely-unused remainder of an aging credit is forfeited; (3) a notification fires on actual expiry (no advance warning). Implemented as proposed, `code modules/`-only, not applied to `raw/`:
- New daily schedule [`Comp_Off_Expiry_Check.md`](code%20modules/schedules/Comp_Off_Expiry_Check.md) (mirrors `Timesheet_Reporting`'s pattern — the scan loop lives directly in the schedule, no separate global scan function): for each consultant, walks their Comp Off "Add" credits oldest-first, draws down total historical "Deduct"/"Expire" debits against them in order, and inserts an offsetting `Type_field="Expire"` row for whatever remains unconsumed once a credit's `Added_Time + 30 days` has passed. Self-idempotent since each day's forfeited amount is itself counted as a future debit.
- New function `Cliq.Send_CompOff_Expired_Notification(int consultant_id, decimal expired_days, datetime credited_on)` in [`notification-functions.md`](code%20modules/functions/deluge/notification-functions.md) — not scoped to a single record (a credit isn't tied to one `Timekeeping1`/`Leave_Request` row), so no `Cliq_Status`/`Mail_Status` write-back, same as `Cliq.Send_Timesheet_Approval_Reminder`.
- `Leave_Balance_Record.Type_field` needs a fifth picklist value, `"Expire"` — flagged as an actual schema change in [`Leave_Balance_Record.md`](code%20modules/forms/Leave_Balance_Record.md) (this picklist has no `others option`, unlike `Leave_Master.Leave_Type_Name1`). Confirmed every balance-read site is already unfiltered by `Type_field`, so no read-site changes are needed — an `"Expire"` row reduces balance the same way `"Deduct"` does.
- Two known simplifications documented in `Comp_Off_Expiry_Check.md` rather than solved: the FIFO walk assumes Creator returns `Leave_Balance_Record` query results in `Added_Time` order (no explicit sort in the script — needs runtime verification), and a rejected/returned Comp-Off spend isn't added back into the FIFO queue (conservative failure direction — under-forfeits, not over-forfeits).
- Updated [`Timekeeping1-actions.md`](code%20modules/functions/record-functions/Timekeeping1-actions.md) (new "Expiry" paragraph in the design section) and [`Notification_Mail_Master.md`](code%20modules/forms/Notification_Mail_Master.md) (new `"Comp Off Expired"` type key). New master-data requirements (a `"Comp Off Expired"` `Notification_Mail_Master` row) not yet created, same as the credited-notification row.

### 2026-09-28

- User pasted a new `raw/Omm_Applications.md` (generated 28-Sep-2026 09:15:37, 15,926 lines, up from the 23-Sep-2026 version's 15,300) and asked to sync `code modules/`/`workflow/` only, in the same style as 2026-09-23. Done as five parallel domain passes (Leave; Timekeeping+Comp Off; Assets; Consultant/Client/Admin/Permissions/Connections; Expense), each re-reading its slice of raw in full and reconciling against current `code modules/`/`workflow/`. Two passes hit the session's API rate limit mid-task and were resumed via `SendMessage` once it reset; one resumed agent initially misjudged that a sibling fork was already covering its domain and had to be redirected to do its own work.
- **Headline finding: the "Comp Off" feature proposed as `code modules/`-only on 2026-09-24 is now real in `raw/`**, but with a different trigger literal than proposed — a `Timekeeping1` entry earns credit when `Leave_Type = "Worked on Holiday"` (not `"Comp Off"` as proposed), crediting a separately-looked-up `"Comp Off"` `Leave_Master` balance at `Hours_Worked / 9` days via `Approve`/`Approve_Timesheet`. The `Comp_Off_Expiry_Check` schedule and both new `Cliq.Send_CompOff_{Credited,Expired}_Notification` functions are now real and closely match the proposal. `Leave_Balance_Record.Type_field` really gained the 5th `"Expire"` value. Both open risks flagged in the 2026-09-24 proposal (double-credit via `edit_approval`→re-approve; no balance reversal on cancel) are confirmed still open in `raw/` itself, with no tracking field — now tracked as CONCURRENCY-008/009 (see below).
- **New real defects found in `raw/`'s own Comp Off implementation** (not introduced by Claude, discovered during the sync): `Load`'s "protect a manual Comp Off claim" guard checks `Leave_Type != "Comp Off"`, which is inert since the field is actually ever set to `"Worked on Holiday"` — `Work_Day`'s equivalent guard checks the correct literal, so the two rules are inconsistent (TIMESHEET-EDGE-011). `Comp_Off_Expiry_Check`'s `spent_rows` query has an unparenthesized `&&`/`||` precedence bug that, after full arithmetic derivation, **under-forfeits** other consultants' expired credit rather than over-forfeiting (DATA-012 — an earlier same-day impression from the sync passes that it over-forfeits was corrected during the dedicated `testing/` pass). `Duplicate_Submission_Hand` (rewritten again for Half/Quarter Day leave blocking via a new `leave_window` helper) has its own precedence bug matching any Submitted leave for the consultant regardless of date (TIMESHEET-EDGE-010).
- **Other real changes found and synced across domains:**
  - Leave: the `Half_Day`/`Half_Day_Session`/`enabling_half_day_session` mechanism (source of LEAVE-EDGE-002/008) was fully removed as of 2026-09-23, replaced by the `Leave_Request_Subform`/`Leave_Request_Subform_Hours` (`Leave1`/`Leave_Hours`) Days/Hours tracking model. New global functions `get_balance_html_hours` and `leave_window`. `Leave_Request.Success` now converts Hours-mode deductions to day-equivalents (÷9) before writing the ledger, but the three Days-mode balance-display sites remain hours-blind (DATA-011). `Success` also does an unscoped `Timekeeping1.Leave_Type` write-back to any matching row (DATA-010). `Cancel3` now correctly writes `"Cancelled"` (was the invalid literal `"Cancel"`) but still never reverses the balance deduction (LEAVE-EDGE-009, new). `Leave_Request.Valid`'s balance-check skip condition widened to `help != "approval"` and now also `help == "reject"`.
  - Timekeeping: `REGRESSION-001` (`Edit_Record1` stale reference) confirmed fixed in `raw/`. `TIMESHEET-EDGE-009` (`Error_Tagging`) confirmed obsolete — the field and mechanism it described no longer exist, replaced by the Comp Off/leave-conflict logic above.
  - Assets: `raw/` independently removed the entire `Attachments` parameter from `Add_Asset`'s and `Asset_Return_Form`'s on-success emails, mooting both ASSET-EDGE-004 (duplicate attachment) and ASSET-EDGE-005 (missing damage photos) — superseded by a new, more severe ASSET-EDGE-007 (all three asset forms now send zero attachments). New `Img_*` photo-upload validation rules (via `isValidImage`/`validation_errors`) let every second invalid upload through due to a marker-toggle bug (ASSET-EDGE-006, new). CONSULTANT-EDGE-001/004 and SECURITY-002 re-verified unchanged.
  - Expense module (`Expense_Report`, `Expense_Subform`, `Expense_Category`, `Trip_Report`): re-synced, no `testing/` findings filed yet for this domain — out of scope for this round's reconciliation pass.
- **`testing/`/`fixes/` reconciliation** (explicitly requested as a distinct follow-on step, covering the backlog from both the 2026-09-23 and 2026-09-28 regenerations, since 2026-09-23's sync deliberately left `testing/`/`fixes/` untouched): done as three parallel passes (Leave/Balance; Timekeeping/Comp Off; Assets/Consultant/Security), each re-deriving conclusions from current `raw/`/`code modules/` rather than trusting the domain-sync summaries alone, followed by a coordinator consistency check across `testing/README.md`, `testing/TODO.md`, and `fixes/TODO.md` (all three passes' concurrent edits to the shared rollup files merged cleanly with no Test ID collisions).
  - **Obsoleted** (mechanism removed from `raw/`, not fixed by Claude): LEAVE-EDGE-002, LEAVE-EDGE-008, TIMESHEET-EDGE-009.
  - **Confirmed still Fixed/Resolved, re-verified against current `raw/`:** DATA-001, CONCURRENCY-005, ASSET-EDGE-001, REGRESSION-001 (newly flipped to Fixed this round).
  - **Superseded:** ASSET-EDGE-004 and ASSET-EDGE-005 by the new ASSET-EDGE-007.
  - **12 new findings filed**, each with a full `testing/` entry and a `fixes/<ID>.md` file: DATA-010 (unscoped `Timekeeping1.Leave_Type` write-back), DATA-011 (Days/Hours balance-display drift), DATA-012 (Comp Off expiry under-forfeit bug), CONCURRENCY-007 (Leave/Timekeeping overlap checks are point-in-time only, not retroactive), CONCURRENCY-008 (Comp Off double-credit via `edit_approval` re-approve), CONCURRENCY-009 (no balance reversal on cancel of a credited entry), LEAVE-EDGE-009 (`Cancel3` never reverses balance), TIMESHEET-EDGE-010 (`Duplicate_Submission_Hand` precedence bug), TIMESHEET-EDGE-011 (`Load`'s inert Comp Off guard), ASSET-EDGE-006 (image-validation toggle bug), ASSET-EDGE-007 (zero email attachments on all three asset forms), KNOWN-003 (vestigial dead assignment in the Comp Off credit insert).
  - Most new fixes are `Proposed`; several (CONCURRENCY-007/008/009, ASSET-EDGE-007) explicitly say they need a business-owner decision rather than inventing one, per the standing rule against inventing business requirements.
  - Not done in this pass: no `testing/` domain was opened for the Expense module's already-documented known issues (no approval flow, placeholder picklists, wrong subtotal on row delete, debug alert, no non-admin permissions) — flagged for a future round.
