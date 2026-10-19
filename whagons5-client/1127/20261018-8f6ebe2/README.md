# Personal spaces and sidebar stacks, client PR 1127

Application head: `8f6ebe2923aa34e981a546f6739133c00ef3c60d`. Captured October 18, 2026 from the actual isolated local app.
Comparison before frontend and backend: staging `71b6bfc445f5cef4a99756942477b8a8d40cda7d`.
Current staging `7a3715a8df20e0fc395daff35eebe757644d66f5` changes review automation only and merges cleanly with this head.

## Environment

- App URL: `http://99d02584-6500-639c-96ef-5612a33e6b32.localhost:5227`.
- Private test project: `5fab8381-a64a-44c8-a2af-57488c7e4ab6`; tenant contains only synthetic fixtures.
- Node 22.19.0, Vite 8.2.2 in e2e mode, published @gonvex/client 0.5.2-staging.29 with the combined patch, isolated Rust runtime, PostgreSQL 17.11 and Firebase Auth emulator.
- Runtime ELF Build ID `36bbf1d0afd1bdbddeb44a77797a3a9d964f6db3`; module-host Build ID `8b3327dd532bf407ed64e4d3f15e29b0298a0bd8`. Reused local binaries are identified by these IDs, not attributed to an unverified framework source commit.
- Exact application bundle SHA256: `4416c239e69c9de6b1270f6c73575f3634d06a5525e1cc4f29d24fd2db407102`.
- Synthetic ordinary Owner, Shared and Receiver Members, fixture prefix Daily. No production login or tenant data.
- Chromium 148.0.7778.96, desktop 1280x800; phone viewport 390x844, not a physical phone.
- One owned browser at a time, capped at 3 GiB and 300% CPU, nice 10, idle IO, no core dumps. The recorded browser-process audit found no escapes or OOM.

## Real UI path and observations

Start from a normal workspace. Right-click its sidebar entry, choose Create personal space and name My reports. Create an own-team task. Config > Task creation restricts the source template and sets Report task; save, reload and create a receiving-team report. Config > Sharing adds a Member by exact email and a receiving team. Saved settings remain after reload. A private task's Share control links to these sharing settings.

Create Follow-ups and another task. Right-click > Stack spaces, select My reports with the keyboard and create My work. One personal sidebar stack shows three tasks from both spaces, deduplicated. Reload, open the actual Edit stack / Unstack spaces menu, rename, verify source-template selection and unstack. At 390x844, exactly three task cards appear without horizontal document overflow. The sidebar is unpinned; the menu/dialog handoff stays open while the pointer enters it.

Sign in as the receiving Member and open the normal receiving space. The same reported source task appears once. Sign in as the shared Member and open the private task's exact location. Use Profile > Appearance > preferred language to select Spanish, open the task, inspect Details and Activity, then repeat the detail sheet at phone size. Switch the actual preference back to English and inspect the phone sheet. Interface labels follow the locale, including Created/Updated/Team and activity text. Spot remains the product term in Spanish, matching the existing web terminology contract. English fixture task names, team names and custom space/verb text are user-entered content, not untranslated interface labels.

Both repository personal-space UI scenarios passed unchanged on this head, one worker and no retries. They additionally exercise receiving-team action, read-only settings, individual/team revocation and persistence. The separate full recorded walkthrough also completed on this head. No full E2E suite was run.

## Media provenance

The English phone screenshot was retaken in a fresh 390x844 browser context at this same head after the full walkthrough and focused scenarios. Saved sharing was verified after reload, followed by a real shared Member login and opening the private task.

Every after PNG and clip uses this exact application head. The before screenshot and clip run the actual comparison application and show the old right-click menu. No after image was taken from a mocked page or an older head. Videos are trimmed from the real UI recording; playback choices and source intervals are listed below. Each clip is one continuous trimmed source interval with the playback scaling below. No internal cuts or fabricated UI states were used. All PNGs and video/GIF sample frames were visually inspected before publication.

```json
[
  {
    "name": "before",
    "start": 4.632,
    "end": 10.918,
    "playbackSlower": 1.0,
    "output": "before.mp4",
    "publishedDuration": 6.32
  },
  {
    "name": "after-create",
    "start": 8.463,
    "end": 13.406,
    "playbackSlower": 1.6,
    "output": "after-create.webm",
    "publishedDuration": 7.92
  },
  {
    "name": "after-stack",
    "start": 38.382999999999996,
    "end": 43.188,
    "playbackSlower": 1.5,
    "output": "after-stack.webm",
    "publishedDuration": 7.24
  }
]
```

## Limits and release

The continuous creation clip briefly shows Space unavailable before the newly created workspace replica arrives and its empty task view opens. The walkthrough then creates tasks successfully. This transient loading message is an open item outside the requested locale/stacking repair scope.

An external AI provider was not configured locally. Browser logs include server-only local-prediction fallbacks. The evaluation selector is absent on staging and needs a separate feature port. These media are evidence for the actual AI visual reviewer; they do not grant owner approval or release the image gate.
