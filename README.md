# Manual QA Portfolio

This repository is a working collection of my manual testing practice: bug reports, test documentation, checklists, and exploratory testing notes.

I focus on clear reproduction steps, verifiable observations, practical risk assessment, and evidence that is safe to share publicly. Missing information is marked honestly instead of being reconstructed from memory.

## Selected work

| Area | Example |
|---|---|
| Bug reporting | [ChatGPT inserts an unrelated Chinese character into an automatically generated Russian title](bug-reports/mobile-ios/MOBILE-IOS-001-cyrillic-title-character.md) |
| Bug reporting — ChatGPT | [Missing final response after completed tool execution on iOS](bug-reports/chatgpt/CHATGPT-IOS-001-empty-response-after-tool-execution.md) |
| Attachment-workflow and keyboard-state testing | [ChatGPT iOS keyboard obstructs the photo picker during multi-image selection](bug-reports/chatgpt/CHATGPT-IOS-005-keyboard-obstructs-photo-picker.md) |
| Field workflow testing | [Amazon Flex apartment-location state desynchronization](bug-reports/amazon-flex/AMAZON-FLEX-001-apartment-location-state-desync.md) |
| Field workflow testing | [Amazon Flex incorrect delivery pin requiring manual relocation](bug-reports/amazon-flex/AMAZON-FLEX-002-incorrect-pin-requires-manual-relocation.md) |
| Field workflow testing | [Amazon Flex package-scanner flashlight state regression](bug-reports/amazon-flex/AMAZON-FLEX-003-scanner-flashlight-state-resets-between-stops.md) |
| Cross-channel consistency testing | [Amazon Flex cancellation email references the wrong station while the block remains active](bug-reports/amazon-flex/AMAZON-FLEX-004-cancellation-email-references-wrong-station-active-block.md) |
| Cross-view UX regression testing | [Amazon Flex delivery urgency status is missing from the itinerary list](bug-reports/amazon-flex/AMAZON-FLEX-005-delivery-urgency-status-missing-from-itinerary-list.md) |
| Safety-workflow testing | [Amazon Flex `Report a problem` control is unresponsive on a delivery stop](bug-reports/amazon-flex/AMAZON-FLEX-006-report-a-problem-button-unresponsive-on-delivery-stop.md) |
| Return-workflow persistence testing | [Amazon Flex `Return now` workflow disappears before packages are returned to the station](bug-reports/amazon-flex/AMAZON-FLEX-007-return-now-workflow-disappears-unexpectedly.md) |
| Navigation-state testing | [Amazon Flex navigation remains in route recalculation after apparent arrival](bug-reports/amazon-flex/AMAZON-FLEX-008-navigation-state-remains-active-after-apparent-arrival.md) |
| Gesture and panel-state testing | [Amazon Flex delivery-map bottom sheet changes position without an intentional drag](bug-reports/amazon-flex/AMAZON-FLEX-009-bottom-sheet-changes-position-without-intentional-drag.md) |
| Timing and notification testing | [DeliverThat escalation warnings precede the stated delivery-start window](bug-reports/deliverthat-ios/DELIVERTHAT-IOS-001-premature-start-warning-conflicts-with-pickup-window.md) |
| Mobile navigation testing | [Apple Maps device lock immediately after navigation starts](bug-reports/apple-maps-ios/APPLE-MAPS-IOS-001-screen-locks-during-active-navigation.md) and [route termination after network loss](bug-reports/apple-maps-ios/APPLE-MAPS-IOS-002-active-route-terminates-after-network-loss.md) |
| Navigation handoff and address-consistency testing | [Apple Maps opens a neighboring destination when launched from Uber Eats](bug-reports/uber-eats-ios/UBER-EATS-IOS-001-apple-maps-opens-neighboring-destination.md) |
| Real-world map-camera stability testing | [Uber Eats map rotates and changes zoom repeatedly after orientation correction](bug-reports/uber-eats-ios/UBER-EATS-IOS-002-map-camera-rotates-and-zooms-after-orientation-control.md) |
| Localization and contextual-control testing | [Amazon Flex customer-notes translation control is no longer displayed](bug-reports/amazon-flex/AMAZON-FLEX-010-customer-notes-translate-control-missing.md) |
| Navigation handoff and destination-data testing | [Apple Maps opens multiple unrelated addresses when launched from Instacart Shopper](bug-reports/instacart-ios/INSTACART-IOS-001-apple-maps-opens-multiple-unrelated-addresses.md) |
| Account-state and deep-link testing | [Veho Driver moves an active account to the waitlist while notification navigation remains intermittently accessible](bug-reports/veho-ios/VEHO-IOS-001-active-account-moves-to-waitlist-while-offer-navigation-remains-accessible.md) |
| Mobile text-editing testing | [Gmail usually prevents cursor placement after a line-initial `I` or `i`](bug-reports/gmail-ios/GMAIL-IOS-001-cursor-cannot-usually-be-placed-after-line-initial-i.md) |
| Shopping-workflow and product-data testing | [Spark Driver displays unidentifiable items with missing product data during an active shopping order](bug-reports/spark-driver-ios/SPARK-IOS-001-unidentifiable-items-missing-product-data.md) |
| Scheduled-order timestamp and data-integrity testing | [DoorDash reports a catering pickup as 1431 minutes early despite timestamps showing it occurred nine minutes after the target](bug-reports/doordash-ios/DOORDASH-IOS-001-scheduled-catering-pickup-reported-1431-minutes-early.md) |
| System-level and in-app state synchronization testing | [Uber Driver remains shown as online in Dynamic Island after the driver goes offline](bug-reports/uber-driver-ios/UBER-DRIVER-IOS-001-dynamic-island-remains-online-after-going-offline.md) |
| Location and account-state testing | [Find My location sharing stops after an uncommunicated sign-out](bug-reports/find-my-ios/FIND-MY-IOS-001-location-sharing-stops-after-silent-sign-out.md) |
| Cross-application mobile testing | [YouTube PiP playback becomes unresponsive after switching to navigation](bug-reports/youtube-ios/YOUTUBE-IOS-001-pip-playback-unresponsive-after-app-switch.md) |
| Intermittent media-state testing | [YouTube video changes unexpectedly during PiP playback while navigation is in use](bug-reports/youtube-ios/YOUTUBE-IOS-003-video-changes-unexpectedly-during-pip-navigation.md) |
| Cross-application resource-state testing | [YouTube PiP controls are unavailable while another application is using the camera](bug-reports/youtube-ios/YOUTUBE-IOS-004-pip-controls-unavailable-during-camera-capture.md) |
| Web media-session testing | [VK Video leaves a second uncontrollable audio stream playing after the visible player is paused](bug-reports/vk-video-ios/VK-VIDEO-IOS-001-uncontrollable-duplicate-audio-after-pause.md) |
| Mobile gesture and editing testing | [Apple Files freezes after an edge gesture during inline rename](bug-reports/apple-files-ios/APPLE-FILES-IOS-001-edge-gesture-freezes-inline-rename.md) |
| Test design | [Test cases](test-cases/README.md) and [test scenarios](test-scenarios/README.md) |
| Exploratory testing | [Charters and session reports](exploratory-testing/README.md) |
| Checklists | [Localization testing checklist](checklists/localization-checklist.md) |

## How I work

- I separate observations from assumptions.
- I write steps that another tester can follow.
- I assess severity by user and product impact.
- I treat priority as a product decision, not a synonym for severity.
- I redact personal and account information before publishing evidence.
- I keep drafts clearly marked until the missing details are verified.

## Repository guide

| Directory | Contents |
|---|---|
| [`bug-reports`](bug-reports/README.md) | Defect reports grouped by product area |
| [`test-cases`](test-cases/README.md) | Detailed, execution-ready test cases |
| [`test-scenarios`](test-scenarios/README.md) | High-level coverage and end-to-end flows |
| [`exploratory-testing`](exploratory-testing/README.md) | Charters and time-boxed session notes |
| [`checklists`](checklists) | Reusable testing checklists |
| [`templates`](templates) | Templates used across the portfolio |
| [`documentation`](documentation) | Reporting standards and assessment rules |

Historical reports use a documented [OS-version inference policy](documentation/historical-os-version-inference.md): official release timing may be added as context, but never substituted for missing device telemetry.

## Current status

The repository is actively maintained. New material is added when it is supported by a real test session, reproducible behavior, or documented evidence.
