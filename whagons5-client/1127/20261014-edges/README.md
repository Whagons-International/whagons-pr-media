# Personal spaces and sidebar stacks, refreshed review

Captured October 14, 2026 for Whagons client PR #1127 after the selection-edge review and staging reconciliation. All data is synthetic, in one isolated local tenant. The owner, shared member and receiving member have ordinary Member roles. No production service or customer data was used.

- Captured and tested application head: `c08189195dbcbf310b4f9207d8b6ea354c233869`.
- Final PR head `6069f900924bbf50f636f370fc9de07af6914bd5` only pins the generated manifest project to CI. Captured application code and runtime are unchanged.
- Comparison frontend: staging `465d15bc70461ec94c5006ca65daf323b0bcfe89`.
- Runtime: pinned Rust Gonvex v2, framework `531a15601b7988732c0104c7c972a0588dfebecc`, Firebase Auth emulator, disposable local PostgreSQL.
- Screens: desktop 1280×800 CSS pixels, mobile 390×844. Chromium on Linux.
- Before and after use the same Daily Own and Daily Receiving prerequisites. Feature-specific dialogs have no equivalent state on staging.
- The owner-provided `before-selection-edges.png` is the original review image at application head `765adbf54a194e8df3744bf4a4de8155c40ccf07`. It is distinct from the staging sidebar comparison.
- This revision replaces the entire active after evidence set, including GIF previews and original recordings. The original private assets revision remains historical and is not the approval walkthrough.

## Observed behavior

1. Normal workspace, sidebar right-click. The staging sidebar has no personal-space creation or stack action. Its hover sidebar closes the old context menu during capture; the original owner-provided edge image supplies the direct selection comparison. After opens Create personal space. Creating My reports displays a lock and Personal label, with no default task type.
2. Create a private own-team task. Save Task creation with the receiving template only and Report task as the button text. Both settings persist after reload. The creation dialog offers the receiving template and excludes the own-team template.
3. Report a task. My reports contains the private task and the reported source task. The receiving team sees the same report once in its normal space. Creating a report does not duplicate the task.
4. Save individual and team sharing. Both remain selected after reload. A private task's Share action links directly to the space's Sharing settings. A shared Member opens the task and sees its exact synthetic location.
5. Create Follow-ups with an own-team task. Right-click Stack spaces, select My reports with the keyboard, and save My work. The keyboard focus outline stays inside the selected rounded card. The stack contains exactly three deduplicated tasks. Reload preserves it, rename/edit works, and Unstack restores the two source entries.
6. Create from the stack asks for the source space, then respects that space's template choices. At 390×844, the same three tasks appear without horizontal document overflow.

The two repository end-to-end tests additionally cover unauthorized access, unknown email validation, zero allowed templates, receiving-team status changes, individual and team revocation across live sessions, deleted personal spaces, fresh session restoration, private stack preferences, inaccessible-stack empty state, and task counts.

## Clips

`before.mp4` and `before.gif` show the old sidebar right-click actions. `after-create.webm` and `after-create.gif` show creation from the sidebar. `after-stack.webm` and `after-stack.gif` show keyboard selection and the resulting combined task view. Setup and login are cut. Slowed playback is stated in the PR captions. Original clips are linked beside each GIF.

## Checks

- Final backend checks passed, including TypeScript, function and metadata checks, architecture, host-call, schema and migration audits, script regressions, and all 2,920 tests in 243 module files.
- All 37 affected frontend tests in eight files passed after the final staging fleet integration. The full frontend suite had passed all 4,220 tests in 831 files at `b86ebba40`, before that integration.
- Frontend TypeScript completed with zero errors, with budget zero unchanged.
- i18n consistency and committed Gonvex generated-artifact checks passed. Migration audit passed with 91 immutable migrations and 170 permission decisions.
- Final repository end-to-end run: both tests passed against the captured application bundle.
