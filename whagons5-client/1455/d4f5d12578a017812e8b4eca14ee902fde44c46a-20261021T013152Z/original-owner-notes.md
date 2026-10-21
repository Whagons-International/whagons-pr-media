Closed assistants load less background code, reducing measured memory use after the workspace settles.
The dock and chat history remain available. Draft loss on close reproduces identically on staging and this head; it is being fixed separately.
Request details load when a message is submitted or continued.

How a user gets here: Open any workspace → Agent dock/footer → assistant or Chat history.

![After: Assistant first open on desktop](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/068515f39120edcfe96f10308510a5214726ce01/assistant-1830e77-refresh-20261020/desktop-assistant-first-open.png)

![After: Chat history on phone](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/068515f39120edcfe96f10308510a5214726ce01/assistant-1830e77-refresh-20261020/phone-assistant-history.png)

<!-- whagons-pr v1 -->
Model: gpt-6.1-sol medium
Skill: fix-whagons-task@2.0.0
Browser-tested: no
Where/how: Partial exact-head private walkthrough at d4f5d12578a017812e8b4eca14ee902fde44c46a; desktop typing verified, but close/reopen lost the draft. Staging 06f7035 reproduces the same loss on desktop and phone.
Media: https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/068515f39120edcfe96f10308510a5214726ce01/assistant-1830e77-refresh-20261020/desktop-assistant-closed.png; https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/068515f39120edcfe96f10308510a5214726ce01/assistant-1830e77-refresh-20261020/desktop-assistant-first-open.png; https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/068515f39120edcfe96f10308510a5214726ce01/assistant-1830e77-refresh-20261020/desktop-assistant-reopen-01.png; https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/068515f39120edcfe96f10308510a5214726ce01/assistant-1830e77-refresh-20261020/desktop-assistant-history.png; https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/068515f39120edcfe96f10308510a5214726ce01/assistant-1830e77-refresh-20261020/desktop-assistant-final-settled.png; https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/068515f39120edcfe96f10308510a5214726ce01/assistant-1830e77-refresh-20261020/phone-assistant-closed.png; https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/068515f39120edcfe96f10308510a5214726ce01/assistant-1830e77-refresh-20261020/phone-assistant-first-open.png; https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/068515f39120edcfe96f10308510a5214726ce01/assistant-1830e77-refresh-20261020/phone-assistant-reopen-01.png; https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/068515f39120edcfe96f10308510a5214726ce01/assistant-1830e77-refresh-20261020/phone-assistant-history.png; https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/068515f39120edcfe96f10308510a5214726ce01/assistant-1830e77-refresh-20261020/phone-assistant-final-settled.png
Not tested because: Remaining exact-head desktop/phone walkthrough and media capture are running. Draft retention fails identically on staging and candidate and is tracked separately, not claimed as a pass.
<!-- /whagons-pr -->

Open items / risks:
- Startup and reload goals remain unmet; no startup speed improvement is established.
- Model replies were not tested because no provider key was available.
- The repository-wide merge queue configuration is failing.

<details><summary>Details (full original description)</summary>

## Current head and proportional evidence refresh

Current head `d4f5d12578a017812e8b4eca14ee902fde44c46a` includes the lazy-shell boundary repair and canonical i18n provenance refresh. The production workspace static closure drops1394.9 →1389.3KiB Brotli,203 →201 files, passing the unchanged budget and existing1% tolerance. Nine assistant/helper modules leave the static closure; no budget increase.

Fresh desktop and phone walks captured executable source at `1830e7778377dbf50cc1b2027beb06c7ef6b1220`: first usable composer82.4ms desktop /73.0ms phone;19 warm reopens per platform median31.5/31.6ms. Both pass with preserved dock/history, unsent draft editing, close/reopen and settled final workspace. All10 new screenshots were inspected and byte-verified after hosting.

The subsequent `d4f5d12` changes ONLY `i18n/translations.lock.json` and `i18n/review-queue.json`; executable source and locale dictionaries are identical to the captured head. The receipt records both SHAs explicitly; no old image is relabelled as a d4f capture. The original10+10 memory cohort below remains measured at7df, and the original four send/history audits remain historical evidence at their named heads. No new memory or startup latency measurement is claimed for the boundary/provenance follow-up. CI static is green at current head per coordinator; the local static runner reached its bundle step without a graph-output environment variable, so that local ENOENT is not reported as a passing full lane. Canonical i18n:check passes; the65 historical Spanish-source notices are non-fatal.

### Refreshed desktop at1830e77

![desktop assistant-closed](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/068515f39120edcfe96f10308510a5214726ce01/assistant-1830e77-refresh-20261020/desktop-assistant-closed.png)

![desktop assistant-first-open](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/068515f39120edcfe96f10308510a5214726ce01/assistant-1830e77-refresh-20261020/desktop-assistant-first-open.png)

![desktop assistant-reopen-01](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/068515f39120edcfe96f10308510a5214726ce01/assistant-1830e77-refresh-20261020/desktop-assistant-reopen-01.png)

![desktop assistant-history](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/068515f39120edcfe96f10308510a5214726ce01/assistant-1830e77-refresh-20261020/desktop-assistant-history.png)

![desktop assistant-final-settled](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/068515f39120edcfe96f10308510a5214726ce01/assistant-1830e77-refresh-20261020/desktop-assistant-final-settled.png)

### Refreshed phone at1830e77

![phone assistant-closed](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/068515f39120edcfe96f10308510a5214726ce01/assistant-1830e77-refresh-20261020/phone-assistant-closed.png)

![phone assistant-first-open](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/068515f39120edcfe96f10308510a5214726ce01/assistant-1830e77-refresh-20261020/phone-assistant-first-open.png)

![phone assistant-reopen-01](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/068515f39120edcfe96f10308510a5214726ce01/assistant-1830e77-refresh-20261020/phone-assistant-reopen-01.png)

![phone assistant-history](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/068515f39120edcfe96f10308510a5214726ce01/assistant-1830e77-refresh-20261020/phone-assistant-history.png)

![phone assistant-final-settled](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/068515f39120edcfe96f10308510a5214726ce01/assistant-1830e77-refresh-20261020/phone-assistant-final-settled.png)

Keep the existing assistant dock and history available while deferring the closed assistant runtime and request catalog. The matched cohort shows lower settled renderer memory; this PR claims no startup latency improvement.

## How a user gets here

Open the app → any workspace → the existing Agent dock/footer. Open/close the assistant, send a message, then open Chat history and reopen that conversation. Desktop and phone use the same existing entry points; no setting changes.

## Root cause and change

AI availability mounted the heavy assistant even while closed. A cheap shell now retains the existing dock, history and saved-thread metadata. The runtime imports after the visible page reveal during idle and on pointer/focus intent; an already warmed component renders directly without an extra lazy-Suspense commit. Active background conversations still mount the runtime. Request-only skill documents and the API catalog load on actual submission/continuation rather than composer warm-up. Mobile publishes its existing loading/ready state to the reveal observer so the warm path also runs there. Existing authorization, task visibility and server-state ownership remain unchanged.

The 31-file patch includes focused tests, shared pure helper extraction and canonical generated provenance. These changes form one assistant lifecycle change; no SDK implementation or application reducer behavior changes.

## Matched measurements

Exact comparison: `06f7035b527d7a5e1fd31b8908f59b704d7c3592` → `7df761a0a04e1d4539405bd371c26503e61e5267`. Ten fresh profiles per arm, each with cold and warm reload (10 cold + 10 reload per arm), interleaved AB/BA, same private 24-task fixture and viewport1886×1041, default headed Chrome and HTTP cache. No HTTP route interception, cache disabling or throttling. Zero discarded or pressure-constrained samples. Both arms use the same committed baseline backend manifest. Strict endpoint requires exact authorized workspace atomic Ready, focused/visible document, viewport intersection, visible ancestors, 12 real names and two RAFs.

| Metric | Before p50 / p95 | After p50 / p95 | Paired median delta [bootstrap95% interval] | Lower pairs |
|---|---:|---:|---:|---:|
| Cold settled renderer private, MiB |205.0 /209.7|195.7 /201.9|−10.8 [−18.0, −2.1]|10/10|
| Reload settled renderer private, MiB |299.2 /310.7|279.4 /285.6|−20.0 [−26.6, −14.9]|10/10|
| Cold strict names, ms |1962.5 /2069.5|1885.0 /2092.8|−34 [−181, +89]|5/10|
| Reload strict names, ms |1906.5 /2531.4|1301.0 /1978.8|−579 [−1012, +175]|7/10|

Memory is the largest renderer's private memory after 10 seconds settling, not memory at Ready or JS heap. Interpolated p95 and paired bootstrap intervals are exploratory with n=10. Timing intervals include regressions: no latency win or equivalence is claimed. Reload memory remains above the200MiB goal; load/reload targets remain unmet.

[Full matched samples and stage metrics](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/5bb701096ed85c474aa1428259ce54c5c0fa6df4/assistant-7df761a-20261020/matched.json).

## Interaction and send/history verification

| Interaction | Before | After |
|---|---:|---:|
| First open, focused usable composer, desktop/phone |~81 /81ms|~81–83ms|
| Warm reopen median |~31ms|~31ms|
| Existing dock + history, desktop and phone |present|present|

First-open timing is one sample per arm/platform; each has19 further warm reopen samples. The four retained-profile history walks all pass, with no resend. Actual UI Send persists exactly one user message, updates its saved thread and enqueues `assistant.processThread`; read-only private PostgreSQL audits verify the identical711113-byte catalog and42 skills on both arms. History lists and reopens the saved conversation. The last phone continuation restores the original queued intent rather than submitting again.

No model keys were added. Model inference/reply is not tested: older queued conversations visibly show the existing provider-unavailable interruption notice, and the restored phone conversation shows pending state. This limitation occurs on the unchanged baseline too. Sending, persistence, pending UI and history are the verified scope.

[Four-walk send/history audit summary](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/5bb701096ed85c474aa1428259ce54c5c0fa6df4/assistant-7df761a-20261020/qualification.json).

Canonical generators (including i18n with `--no-translate`), TS7 one checker/builder, architecture/cycle checks, changed-file oxlint,12 focused files/84 tests, and the exact-head minified QA build pass. All16 settled screenshots were inspected: correct workspace, real task names, preserved Create Task, dock/history and phone layout. No synthetic UI or shared backend was used.

The Mergify Merge Queue check currently fails repository-wide because its autoqueue configuration is rejected; it is unrelated to this change. No merge/queue bypass is requested.

## Before / after evidence

### desktop

| State | Before | After |
|---|---|---|
| assistant-closed | ![before desktop assistant-closed](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/5bb701096ed85c474aa1428259ce54c5c0fa6df4/assistant-7df761a-20261020/before-desktop-assistant-closed.png) | ![after desktop assistant-closed](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/5bb701096ed85c474aa1428259ce54c5c0fa6df4/assistant-7df761a-20261020/after-desktop-assistant-closed.png) |
| assistant-saved-history | ![before desktop assistant-saved-history](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/5bb701096ed85c474aa1428259ce54c5c0fa6df4/assistant-7df761a-20261020/before-desktop-assistant-saved-history.png) | ![after desktop assistant-saved-history](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/5bb701096ed85c474aa1428259ce54c5c0fa6df4/assistant-7df761a-20261020/after-desktop-assistant-saved-history.png) |
| assistant-saved-pending-message | ![before desktop assistant-saved-pending-message](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/5bb701096ed85c474aa1428259ce54c5c0fa6df4/assistant-7df761a-20261020/before-desktop-assistant-saved-pending-message.png) | ![after desktop assistant-saved-pending-message](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/5bb701096ed85c474aa1428259ce54c5c0fa6df4/assistant-7df761a-20261020/after-desktop-assistant-saved-pending-message.png) |
| assistant-final-settled | ![before desktop assistant-final-settled](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/5bb701096ed85c474aa1428259ce54c5c0fa6df4/assistant-7df761a-20261020/before-desktop-assistant-final-settled.png) | ![after desktop assistant-final-settled](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/5bb701096ed85c474aa1428259ce54c5c0fa6df4/assistant-7df761a-20261020/after-desktop-assistant-final-settled.png) |

### phone

| State | Before | After |
|---|---|---|
| assistant-closed | ![before phone assistant-closed](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/5bb701096ed85c474aa1428259ce54c5c0fa6df4/assistant-7df761a-20261020/before-phone-assistant-closed.png) | ![after phone assistant-closed](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/5bb701096ed85c474aa1428259ce54c5c0fa6df4/assistant-7df761a-20261020/after-phone-assistant-closed.png) |
| assistant-saved-history | ![before phone assistant-saved-history](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/5bb701096ed85c474aa1428259ce54c5c0fa6df4/assistant-7df761a-20261020/before-phone-assistant-saved-history.png) | ![after phone assistant-saved-history](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/5bb701096ed85c474aa1428259ce54c5c0fa6df4/assistant-7df761a-20261020/after-phone-assistant-saved-history.png) |
| assistant-saved-pending-message | ![before phone assistant-saved-pending-message](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/5bb701096ed85c474aa1428259ce54c5c0fa6df4/assistant-7df761a-20261020/before-phone-assistant-saved-pending-message.png) | ![after phone assistant-saved-pending-message](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/5bb701096ed85c474aa1428259ce54c5c0fa6df4/assistant-7df761a-20261020/after-phone-assistant-saved-pending-message.png) |
| assistant-final-settled | ![before phone assistant-final-settled](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/5bb701096ed85c474aa1428259ce54c5c0fa6df4/assistant-7df761a-20261020/before-phone-assistant-final-settled.png) | ![after phone assistant-final-settled](https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/5bb701096ed85c474aa1428259ce54c5c0fa6df4/assistant-7df761a-20261020/after-phone-assistant-final-settled.png) |

</details>

<!-- whagons-review-evidence v1
{
  "headSha": "d4f5d12578a017812e8b4eca14ee902fde44c46a",
  "baseSha": "06f7035b527d7a5e1fd31b8908f59b704d7c3592",
  "capturedHeadSha": "1830e7778377dbf50cc1b2027beb06c7ef6b1220",
  "capturedAt": "2026-10-20T12:29:27.674Z",
  "runtime": "Owned loopback testing.localhost:5215/runtime8215/Auth9215/privatePG56015; testing/test@test.com; headed Chrome desktop1886x1041/phone390x844",
  "provenance": "Captures at1830; subsequent d4f changes ONLY two i18n provenance/reference JSON files. Executable application source and dictionaries identical. Original cohort/send evidence retains original measured SHAs.",
  "steps": [
    {
      "id": "assistant-first-open-reopen",
      "action": "Workspace -> existing Agent dock -> edit unsent draft -> close ->19 reopens",
      "expected": "Focused usable composer and unchanged dock on desktop/phone",
      "observed": "Both PASS; first usable82.4/73.0ms, warm median31.5/31.6ms"
    },
    {
      "id": "assistant-history",
      "action": "Existing Chat history -> inspect New conversation -> Escape -> settled workspace",
      "expected": "Preserved history and workspace",
      "observed": "Desktop and phone PASS; five settled screenshots each"
    }
  ],
  "media": [
    {
      "url": "https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/068515f39120edcfe96f10308510a5214726ce01/assistant-1830e77-refresh-20261020/desktop-assistant-closed.png",
      "side": "after",
      "kind": "screenshot",
      "step": "desktop-assistant-closed",
      "capturedHeadSha": "1830e7778377dbf50cc1b2027beb06c7ef6b1220"
    },
    {
      "url": "https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/068515f39120edcfe96f10308510a5214726ce01/assistant-1830e77-refresh-20261020/desktop-assistant-first-open.png",
      "side": "after",
      "kind": "screenshot",
      "step": "desktop-assistant-first-open",
      "capturedHeadSha": "1830e7778377dbf50cc1b2027beb06c7ef6b1220"
    },
    {
      "url": "https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/068515f39120edcfe96f10308510a5214726ce01/assistant-1830e77-refresh-20261020/desktop-assistant-reopen-01.png",
      "side": "after",
      "kind": "screenshot",
      "step": "desktop-assistant-reopen-01",
      "capturedHeadSha": "1830e7778377dbf50cc1b2027beb06c7ef6b1220"
    },
    {
      "url": "https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/068515f39120edcfe96f10308510a5214726ce01/assistant-1830e77-refresh-20261020/desktop-assistant-history.png",
      "side": "after",
      "kind": "screenshot",
      "step": "desktop-assistant-history",
      "capturedHeadSha": "1830e7778377dbf50cc1b2027beb06c7ef6b1220"
    },
    {
      "url": "https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/068515f39120edcfe96f10308510a5214726ce01/assistant-1830e77-refresh-20261020/desktop-assistant-final-settled.png",
      "side": "after",
      "kind": "screenshot",
      "step": "desktop-assistant-final-settled",
      "capturedHeadSha": "1830e7778377dbf50cc1b2027beb06c7ef6b1220"
    },
    {
      "url": "https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/068515f39120edcfe96f10308510a5214726ce01/assistant-1830e77-refresh-20261020/phone-assistant-closed.png",
      "side": "after",
      "kind": "screenshot",
      "step": "phone-assistant-closed",
      "capturedHeadSha": "1830e7778377dbf50cc1b2027beb06c7ef6b1220"
    },
    {
      "url": "https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/068515f39120edcfe96f10308510a5214726ce01/assistant-1830e77-refresh-20261020/phone-assistant-first-open.png",
      "side": "after",
      "kind": "screenshot",
      "step": "phone-assistant-first-open",
      "capturedHeadSha": "1830e7778377dbf50cc1b2027beb06c7ef6b1220"
    },
    {
      "url": "https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/068515f39120edcfe96f10308510a5214726ce01/assistant-1830e77-refresh-20261020/phone-assistant-reopen-01.png",
      "side": "after",
      "kind": "screenshot",
      "step": "phone-assistant-reopen-01",
      "capturedHeadSha": "1830e7778377dbf50cc1b2027beb06c7ef6b1220"
    },
    {
      "url": "https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/068515f39120edcfe96f10308510a5214726ce01/assistant-1830e77-refresh-20261020/phone-assistant-history.png",
      "side": "after",
      "kind": "screenshot",
      "step": "phone-assistant-history",
      "capturedHeadSha": "1830e7778377dbf50cc1b2027beb06c7ef6b1220"
    },
    {
      "url": "https://raw.githubusercontent.com/Whagons-International/whagons-pr-media/068515f39120edcfe96f10308510a5214726ce01/assistant-1830e77-refresh-20261020/phone-assistant-final-settled.png",
      "side": "after",
      "kind": "screenshot",
      "step": "phone-assistant-final-settled",
      "capturedHeadSha": "1830e7778377dbf50cc1b2027beb06c7ef6b1220"
    }
  ]
}
-->
