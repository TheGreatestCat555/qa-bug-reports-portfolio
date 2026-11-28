# AMAZON-FLEX-012: Station scanner displays 1 for every package until the app is restarted

> **Status:** Draft

## Summary

While loading and sorting route packages at a station, the driver used the camera scanner to identify their stop associations. During one episode, every scanned package displayed a small 1 instead of providing useful distinguishing information. The behavior persisted until the driver restarted Amazon Flex.

## Product and platform

- Product: Amazon Flex driver application
- Platform: iOS
- Component: Station package-identification scanner / camera overlays used during route sorting

## Environment

| Field | Value |
|---|---|
| Device | iPhone 14 Pro Max |
| Installed OS | iOS 26.6.1, supplied in the same firsthand account |
| Application version context | 2.617.206 on the supplied App Store page; driver reports the current app is updated |
| Build during the earlier station episode | Not independently captured; the current version is not proof of its installed build |
| Route workflow | Scanning one route package loads the itinerary; individual packages are then scanned for sorting/marking |
| Scanner behavior described | Multiple visible package codes can be recognized by the camera, with small numeric overlays |
| Network | Not recorded for this episode |
| Date documented | November 27, 2026 |
| Date observed | Not specified; one episode reported retrospectively |

## Preconditions

- The driver has loaded the route by scanning a package assigned to it.
- Multiple route packages are being loaded into the vehicle and sorted by their delivery-stop associations.
- The package-identification scanner is available.

## Steps to reproduce

This reconstructs a single field episode. Its trigger has not been isolated.

1. Load the itinerary using the station's scan-one-route-package workflow.
2. Open the package-identification scanner used to associate packages with stops while loading.
3. Present different route packages to the camera, including multiple readable codes when visible.
4. Compare the small numeric overlays and any identifying information returned for each package.
5. If every scanned package displays 1 without useful distinguishing information, restart Amazon Flex.
6. Reopen the workflow and compare package-identification results.

## Actual result

The scanner recognized packages, but every package displayed 1. Scanning did not provide the other information the driver needed to distinguish their route/stop associations. The state persisted during the episode; the driver reports that restarting the app cleared it.

This describes what the interface displayed. It does not prove that all packages were assigned to stop 1 in the underlying route data. The exact semantic meaning of the numeric overlay has not been independently verified.

## Expected result

The identification workflow should provide correct, usable package-to-stop information for sorting. If its numeric overlay denotes a stop or sequence, it should reflect the package's actual association. If it instead denotes quantity or another value, that meaning and the needed identifying information should remain clear; repeated 1 values alone are not proof of a routing error without that distinction.

## Reproducibility

One episode affecting multiple packages before restart. Exact package count and number of scan attempts were not recorded. No controlled repeat has been performed. The four-to-five-day recurrence window described for delivery-stop scan failures is not assigned to this separate event.

## Severity

**Medium candidate.** The displayed results prevented normal package identification for loading/sorting until restart. No misdelivery, damaged route assignment, or permanent data loss was demonstrated.

## Priority

**To be assessed.** Impact on sorting is reported, but overlay semantics, recurrence, and affected versions require verification.

## Category

Functional / Package Identification / Scanner Overlay / State Management / Recovery

## Workaround

Restart Amazon Flex and reopen the scanner. This cleared the reported episode; no broader recovery rate was tested.

## Evidence and limitations

- Firsthand description of the persistent all-1 display and restart recovery.
- The supplied screenshot provides current application-version context only; no screenshot or recording of the all-1 state was supplied.
- Station identifiers, personal information, customer addresses, package codes, and route details are excluded.
- No exact package-to-stop comparison, scanner logs, or route-state export is available.

## Related observations and follow-up

[AMAZON-FLEX-011](AMAZON-FLEX-011-delivery-qr-scanner-unresponsive-until-app-restart.md) concerns no scan response at delivery stops. This episode instead involved recognized packages and unhelpful numeric results at the station. A shared cause is possible but unverified.

On a privacy-safe test route, establish what each overlay represents and compare distinct package IDs with their expected stops before and after restarting. Test single-code and multiple-code views. The driver noticed that scanner presentation had changed in a recent update compared with roughly six months earlier, but this does not establish which update introduced the fault or that the presentation change caused it.
