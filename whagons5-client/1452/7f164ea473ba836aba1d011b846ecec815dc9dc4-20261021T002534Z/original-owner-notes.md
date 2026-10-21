Workspace tasks start loading before the rest of the workspace screen.
Measured cold loads show real task names sooner while existing access checks stay in place.

How a user gets here: Open the app → workspace → Tasks, or reload the workspace.

![After: Workspace tasks on desktop](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/after-desktop-workspace-open.png)

![After: Workspace tasks on phone](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/after-phone-workspace-open.png)

<!-- whagons-pr v1 -->
Model: gpt-6.1-sol medium
Skill: fix-whagons-task@2.0.0
Browser-tested: yes
Where/how: Owned loopback testing.localhost:5215, runtime127.0.0.1:8215, Firebase Auth Emulator9215 and private PostgreSQL56015; testing/test@test.com; default headed Chrome; desktop1886x1041, phone390x844;6G working/7G hard capped unit. Tested head 7f164ea473ba836aba1d011b846ecec815dc9dc4; comparison base 9f74bf0240845934547da4c195b742b9aa6f416e; original successful four journeys with disclosed tour obstruction and rejected baseline-only retry flakes.
Media: https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/before-desktop-workspace-open.png; https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/before-desktop-workspace-switch.png; https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/before-desktop-workspace-reload.png; https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/before-phone-workspace-open.png; https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/before-phone-workspace-switch.png; https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/before-phone-workspace-reload.png; https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/after-desktop-workspace-open.png; https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/after-desktop-workspace-switch.png; https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/after-desktop-workspace-reload.png; https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/after-phone-workspace-open.png; https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/after-phone-workspace-switch.png; https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/after-phone-workspace-reload.png
<!-- /whagons-pr -->

Open items / risks:
- Reload improvement remains unresolved, and cold-load and reload goals remain unmet.
- Desktop switch captures are obstructed by the existing welcome tour.

<details><summary>Details (full original description)</summary>

## What changes

- Request workspace task rows as soon as the admitted workspace route mounts, ahead of the lazy workspace shell.
- Reduce cold load to twelve real task names by about 0.33 s at the median in the clean matched cohort.
- Keep the existing billing, password, authentication and tenant Member gates. No cached rows are rendered or certified by the new component.

## How to test

1. Sign into the private `testing` tenant as `test@test.com`, then open an existing workspace through the sidebar.
2. Confirm real task names and Create Task appear. Switch to another workspace and check that its tasks appear.
3. Reload that workspace, check its task names, then return to the first workspace. Repeat at phone width.
4. If the existing welcome tour appears, use its ordinary Skip tour control before continuing.

## How a user gets here

Open the app -> any workspace -> Tasks; reload the page. No setting or feature flag changes.

## Root cause and scope

The first task watch previously belonged to lazy sidebar/workspace consumers, after unrelated startup work. A small renderless owner inside the existing access gates now starts the same SDK Replica Collection and normalized hydration before AppRouter. It creates no second cache and changes no SDK, visibility policy, offline authority, reducer or task-budget behavior. Non-workspace and unadmitted/signed-out routes skip it.

The measured implementation is `0af0e1140ee6a1ec13e37e1afaf2067c378347f5`. Current pushed/captured head `7f164ea473ba836aba1d011b846ecec815dc9dc4` adds only canonically refreshed i18n lock/review provenance, with the measured implementation byte-identical. No translations were generated. Comparison base is `9f74bf0240845934547da4c195b742b9aa6f416e`.

## Matched measurements

Each cohort has ten fresh profiles per arm, each with cold and warm reload: ten cold plus ten reload samples per side. Arms alternate before/after then after/before. Same small private24-task corpus,1886x1041 viewport, default headed Chrome and default HTTP cache, no HTTP route interception/Fetch cache disabling, no DevTools throttle. Endpoint requires the exact workspace atomic frame Ready, focused/visible document, viewport and visible ancestors, twelve expected real names and two RAFs. All completed runs remain in the tables; no outlier removal. p95 is interpolated with n=10; paired bootstrap intervals are exploratory, not an equivalence test.

### v1

4G working/5G hard. MemoryHigh pressure occurred in8/10 profiles on EACH arm. No max/OOM/CPU-throttle events. This is a resource-constrained lead, not clean qualification.

| Strict endpoint | Before p50 / p95, ms | After p50 / p95, ms | Paired median delta, ms | Bootstrap95% interval | Faster pairs |
|---|---:|---:|---:|---:|---:|
| cold | 2798.5 / 3172.2 | 2165.5 / 3024.6 | -383.0 | [-1047.0, -119.5] | 8/10 |
| reload | 1625.0 / 2145.5 | 1632.0 / 1916.1 | -75.0 | [-120.0, 182.5] | 6/10 |

[Full v1 samples, spreads and stage metrics](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/v1-matched.json).

### v2

6G working/7G hard. Zero pressure-constrained profiles on either arm; zero discarded samples. This clean independent replication qualifies the cold improvement.

| Strict endpoint | Before p50 / p95, ms | After p50 / p95, ms | Paired median delta, ms | Bootstrap95% interval | Faster pairs |
|---|---:|---:|---:|---:|---:|
| cold | 2617.5 / 3172.1 | 2288.5 / 2803.6 | -374.0 | [-671.0, -29.0] | 8/10 |
| reload | 1706.0 / 3877.4 | 1585.0 / 3688.0 | +25.0 | [-351.0, 214.0] | 5/10 |

[Full v2 samples, spreads and stage metrics](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/v2-matched.json).

Reload remains unresolved. Its clean paired interval spans slower and faster results, so this PR claims no reload improvement or equivalence. Reload p95 is still3.69s and its maximum4.80s; the600ms reload and1.3s cold goals are unmet.

In the clean cohort, reload task wire-Ready p50 advances **1586 ->880ms**, and first task wire-open1191 ->448ms. The median per-run wire-Ready-to-strict interval grows88 ->723ms, exposing a later normalized-publication/authorization/mount/commit tail. Wire Ready is not itself a React authority certificate. A separate earlier diagnostic has accepted current/up-to-date tasks947ms, frame1359ms, first grid1568ms and strict1721ms. Another diagnostic had slow auth and later task readiness, so not every reload has the same bottleneck. Next experiment: defer closed AssistantWidget mounting while preserving explicit launch and active background work.

Clean first-grid-commit p50 moves cold1746 ->1454ms, reload1265 ->1279ms; these commits may contain cached/skeleton rows and are NOT the strict endpoint. Opened collections before strict remain134 median on both arms,95 public plus39 generated dependencies. This change advances demand, it does not remove startup fan-out.

Ready JS heap p50: cold56.0 ->52.1MiB; reload69.5 ->67.6MiB. Largest renderer private after10s settling: cold202.9 ->194.2MiB; reload293.0 ->295.1MiB. Full renderer-private memory at Ready was not collected. This is not a memory-budget fix.

## Verification and capture caveat

- Seven task-demand cases plus the existing Settings E2E guard:16 tests pass. Includes task-first order, other routes, delayed Member admission and signed-out cached Member.
- Canonical contract/routes/types/icons/released-app inventories, i18n sync with `--no-translate`, Gonvex generation, architecture baseline, TS7 one checker/builder, focused tests, changed-file oxlint, runtime-cycle comparison and exact-head minified QA build pass. No client-contract version bump.
- Real UI sign-in using the owned Auth Emulator and private testing tenant; original v1 completed before/after desktop and phone open/switch/reload/return journeys at the exact displayed heads. Screenshots were individually inspected. Names, task IDs and workspace A/B match; no empty task lists, app error banners or layout differences were observed.
- **Known capture/harness issue:** both desktop switch images show the pre-existing welcome-tour overlay. They are labelled as obstructed, not clean grid evidence. Desktop open/reload and all phone screenshots are unobscured. Later baseline-only retries flaked when the tour appeared during the Create Task actionability check, then hit a Skip tour locator-handler loop. These rejected retries are not claimed as passing walkthroughs and do not replace the successful original journey. The owner explicitly requested publication with this caveat rather than more reruns.

## Before and after screenshots

### desktop workspace-open

Before

![before desktop workspace-open](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/before-desktop-workspace-open.png)

After

![after desktop workspace-open](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/after-desktop-workspace-open.png)

### desktop workspace-switch (tour overlay in both comparison images)

Before

![before desktop workspace-switch](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/before-desktop-workspace-switch.png)

After

![after desktop workspace-switch](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/after-desktop-workspace-switch.png)

### desktop workspace-reload

Before

![before desktop workspace-reload](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/before-desktop-workspace-reload.png)

After

![after desktop workspace-reload](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/after-desktop-workspace-reload.png)

### phone workspace-open

Before

![before phone workspace-open](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/before-phone-workspace-open.png)

After

![after phone workspace-open](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/after-phone-workspace-open.png)

### phone workspace-switch

Before

![before phone workspace-switch](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/before-phone-workspace-switch.png)

After

![after phone workspace-switch](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/after-phone-workspace-switch.png)

### phone workspace-reload

Before

![before phone workspace-reload](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/before-phone-workspace-reload.png)

After

![after phone workspace-reload](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/after-phone-workspace-reload.png)

<!-- codesmith:footer -->
---
<a href="https://app.blacksmith.sh/Whagons-International/codesmith/whagons5-client/pr/1452?autoLogin=true&ref=codesmith_pr_footer"><picture><source media="(prefers-color-scheme: dark)" srcset="https://pr-comments-assets.blacksmith.sh/codesmith/view-with-codesmith-dark-v3.svg"><source media="(prefers-color-scheme: light)" srcset="https://pr-comments-assets.blacksmith.sh/codesmith/view-with-codesmith-light-v3.svg"><img alt="View with [code]smith" src="https://pr-comments-assets.blacksmith.sh/codesmith/view-with-codesmith-dark-v3.svg"></picture></a> <a href="https://backend.blacksmith.sh/track/enable-autofix?expires=1795078342&installation_model_id=432528&pr_number=1452&ref=codesmith_pr_footer&repository=Whagons-International%2Fwhagons5-client&return_to=https%3A%2F%2Fgithub.com%2FWhagons-International%2Fwhagons5-client%2Fpull%2F1452&signature=ec869571a2ffaee2a6726da50a9b58e19853d12263a3734a777eadaa922a2c54"><picture><source media="(prefers-color-scheme: dark)" srcset="https://pr-comments-assets.blacksmith.sh/codesmith/autofix-with-codesmith-dark.svg"><source media="(prefers-color-scheme: light)" srcset="https://pr-comments-assets.blacksmith.sh/codesmith/autofix-with-codesmith-light.svg"><img alt="Autofix with [code]smith" src="https://pr-comments-assets.blacksmith.sh/codesmith/autofix-with-codesmith-dark.svg"></picture></a>
<sup>Need help on this PR? Tag <code>@codesmith</code> with what you need.</sup>

<!-- codesmith:autofix:disabled -->
<!-- /codesmith:footer -->

</details>

<!-- whagons-review-evidence v1
{
  "headSha": "7f164ea473ba836aba1d011b846ecec815dc9dc4",
  "baseSha": "9f74bf0240845934547da4c195b742b9aa6f416e",
  "capturedAt": "2026-10-20T08:22:55.373Z",
  "runtime": "Owned loopback testing.localhost:5215, runtime127.0.0.1:8215, Firebase Auth Emulator9215 and private PostgreSQL56015; testing/test@test.com; default headed Chrome; desktop1886x1041, phone390x844;6G working/7G hard capped unit.",
  "repro": "Actual UI sign-in -> workspace A -> sidebar workspace B -> reload B -> return A, both arms and desktop/phone. Original v1 completed all four journeys; tour obstruction disclosed; later baseline retries are rejected harness failures.",
  "steps": [
    {
      "id": "desktop-workspace-open",
      "action": "desktop: Sign in and open workspace A",
      "expected": "Correct workspace and populated task surface",
      "observed": "Correct A/B workspace, real task names and matching layout; no visible app error banner."
    },
    {
      "id": "desktop-workspace-switch",
      "action": "desktop: Choose workspace B in the sidebar",
      "expected": "Correct workspace and populated task surface",
      "observed": "Correct A/B workspace, real task names and matching layout; no visible app error banner. Both comparison screenshots contain the pre-existing welcome-tour modal; underlying B rows are obscured. Reload screenshots show unobscured B rows. See capture caveat."
    },
    {
      "id": "desktop-workspace-reload",
      "action": "desktop: Reload workspace B, then return to A",
      "expected": "Correct workspace and populated task surface",
      "observed": "Correct A/B workspace, real task names and matching layout; no visible app error banner."
    },
    {
      "id": "phone-workspace-open",
      "action": "phone: Sign in and open workspace A",
      "expected": "Correct workspace and populated task surface",
      "observed": "Correct A/B workspace, real task names and matching layout; no visible app error banner."
    },
    {
      "id": "phone-workspace-switch",
      "action": "phone: Choose workspace B in the sidebar",
      "expected": "Correct workspace and populated task surface",
      "observed": "Correct A/B workspace, real task names and matching layout; no visible app error banner."
    },
    {
      "id": "phone-workspace-reload",
      "action": "phone: Reload workspace B, then return to A",
      "expected": "Correct workspace and populated task surface",
      "observed": "Correct A/B workspace, real task names and matching layout; no visible app error banner."
    }
  ],
  "media": [
    {
      "url": "https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/before-desktop-workspace-open.png",
      "side": "before",
      "kind": "screenshot",
      "step": "desktop-workspace-open"
    },
    {
      "url": "https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/before-desktop-workspace-switch.png",
      "side": "before",
      "kind": "screenshot",
      "step": "desktop-workspace-switch"
    },
    {
      "url": "https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/before-desktop-workspace-reload.png",
      "side": "before",
      "kind": "screenshot",
      "step": "desktop-workspace-reload"
    },
    {
      "url": "https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/before-phone-workspace-open.png",
      "side": "before",
      "kind": "screenshot",
      "step": "phone-workspace-open"
    },
    {
      "url": "https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/before-phone-workspace-switch.png",
      "side": "before",
      "kind": "screenshot",
      "step": "phone-workspace-switch"
    },
    {
      "url": "https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/before-phone-workspace-reload.png",
      "side": "before",
      "kind": "screenshot",
      "step": "phone-workspace-reload"
    },
    {
      "url": "https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/after-desktop-workspace-open.png",
      "side": "after",
      "kind": "screenshot",
      "step": "desktop-workspace-open"
    },
    {
      "url": "https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/after-desktop-workspace-switch.png",
      "side": "after",
      "kind": "screenshot",
      "step": "desktop-workspace-switch"
    },
    {
      "url": "https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/after-desktop-workspace-reload.png",
      "side": "after",
      "kind": "screenshot",
      "step": "desktop-workspace-reload"
    },
    {
      "url": "https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/after-phone-workspace-open.png",
      "side": "after",
      "kind": "screenshot",
      "step": "phone-workspace-open"
    },
    {
      "url": "https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/after-phone-workspace-switch.png",
      "side": "after",
      "kind": "screenshot",
      "step": "phone-workspace-switch"
    },
    {
      "url": "https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/45091078f212dec1e68991f251d0ade9202627f2/task-first-7f164ea-20261020/after-phone-workspace-reload.png",
      "side": "after",
      "kind": "screenshot",
      "step": "phone-workspace-reload"
    }
  ]
}
-->
