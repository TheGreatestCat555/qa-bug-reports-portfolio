# VK-VIDEO-IOS-001: A second uncontrollable audio stream continues after the visible player is paused

> **Status:** Draft

## Summary

A VK Video page opened from Google Search on an iPhone produced doubled audio with a short offset. Pausing the visible video player did not stop all playback: another audio stream continued without a corresponding visible control, making the remaining playback impossible to pause from the displayed player.

## Product and platform

- Product area: VK Video web playback
- Entry path: Google Search result to a VK Video page
- Platform: iOS

## Environment

| Field | Value |
|---|---|
| Device | iPhone 14 Pro Max |
| OS version/build | Not recorded |
| Browser or in-app browser | Not identified |
| VK application use | Not established; the content was described as a web page opened from search results |
| VK player/page version | Not recorded |
| Network conditions | Not recorded |
| Date documented | May 6, 2026 |
| Exact date observed | Not independently recorded |

## Preconditions

- Google Search is available on the iPhone.
- A search result opens a playable VK Video page.
- Audio output is enabled.

## Steps to reproduce

The issue was observed once and is not predictably reproducible. These steps describe the field workflow rather than a guaranteed reproduction:

1. Search Google for a movie or video on the iPhone.
2. Open a VK Video result.
3. Start playback in the page's visible video player.
4. Listen for doubled audio streams with a short timing offset.
5. Pause the visible video player.
6. Observe whether another audio stream continues without a corresponding visible control.

## Actual result

- Playback audio is heard twice with a short offset.
- Pausing the visible video player does not stop all audio.
- Another stream continues playing the same content.
- The continuing stream cannot be paused or otherwise controlled through the visible player interface.

## Expected result

- The page should create only one synchronized playback stream for the selected video.
- Pausing the visible player should stop its associated video and audio.
- No hidden or independently playing media instance should remain without accessible controls.

## Reproducibility

Observed once. The issue did not have a known trigger and no controlled reproduction attempts or rate were recorded.

## Severity

**Medium candidate.** The duplicated and uncontrollable audio makes playback unusable until the media context is exited or otherwise reset. No data loss, account impact, or safety impact was observed.

## Priority

**To be assessed.** The experience is significantly disrupted when the issue occurs, but frequency, affected browser/container, affected-version range, and user scope are unknown.

## Category

Functional / Media Playback / Audio State / Web Integration

## Workaround

No verified workaround was recorded in the source observation.

## Evidence

- Firsthand verbal field account: available.
- Screen recording: not available.
- Browser, WebView, media-session, console, and network logs: not available.
- Movie title, search terms, account information, and page URL are intentionally excluded.

## Notes and limitations

- The audible symptoms are consistent with more than one active playback stream, but the observation does not establish whether the source was a second video element, a separate audio track, another tab or window, a background media session, or a different mechanism.
- The responsible component cannot be assigned from the available evidence. It may involve the VK player page, its browser or in-app-browser container, iOS media handling, or an interaction among them.
- The exact browser is unknown. It should not be described as Safari unless verified in a future occurrence.
- The exact iOS version was not supplied in the firsthand account. An OS version proposed in the original assistant response is not treated as device telemetry.
- Future verification should capture a privacy-safe screen recording, the exact iOS build, browser/container and version, active tabs or views, Control Center media state, output route, page URL without personal parameters, and whether closing the page stops the remaining stream.

