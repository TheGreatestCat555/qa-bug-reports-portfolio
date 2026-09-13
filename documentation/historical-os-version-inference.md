# Historical OS Version Inference

Exact device telemetry is always preferable to reconstruction. When the OS version was not recorded but an observation date is available, this portfolio may add a separate release-context field based on the vendor's official release history.

## Reporting rules

1. Keep the actual environment field as `Not recorded`.
2. Add a distinct `Official release context` field; never silently replace missing telemetry with an inferred version.
3. State whether the available date is the occurrence date or only the date when the account was documented.
4. Name the latest compatible public release on that date and include its official release date.
5. Treat enabled automatic updates only as evidence that a recent release is plausible—not proof that it was already installed.
6. Preserve alternative supported branches, staged availability, delayed installation, beta participation, managed-device deferral, and rapid security responses when relevant.
7. Do not use release timing to claim causation. Temporal proximity to an update is a hypothesis generator, not proof that the update caused the behavior.
8. Link the primary vendor release record.

## Confidence language

- **Confirmed:** version was captured from device settings, diagnostic data, or contemporaneous evidence.
- **Likely release context:** official timing plus known update settings support the candidate, but installation was not recorded.
- **Compatible candidates:** multiple supported versions or branches remained plausible.
- **Unknown:** the date, hardware compatibility, or release record is insufficient.

## Apple release context used for March–April 2026 reports

According to Apple's official security-release history:

- iOS 26.3.1 was released for iPhone 11 and later on March 4, 2026.
- a Background Security Improvement for iOS 26.3.1 was released March 17, 2026; installation of that response was not recorded on the test device.
- iOS 26.4 was released for iPhone 11 and later on March 24, 2026.
- iOS 18.7.7 was released for the older-version branch on March 24 and made available to additional compatible devices, including iPhone 14 models, on April 1, 2026.
- iOS 26.4.1 was not released until April 8, 2026.

Primary source: [Apple security releases](https://support.apple.com/en-ca/100100).

These dates establish compatible release context only. They do not identify the version that was actually installed on a particular device.
