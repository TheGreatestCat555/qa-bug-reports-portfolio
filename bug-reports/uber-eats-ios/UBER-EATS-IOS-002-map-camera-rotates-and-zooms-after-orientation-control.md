# UBER-EATS-IOS-002: Map camera rotates and changes zoom repeatedly after the orientation control is selected

> **Status:** Draft

## Summary

The built-in map in the Uber Eats driver workflow can display the driver's direction incorrectly. Selecting the map orientation control to correct the heading can then place the camera in an unstable state: the map repeatedly rotates, changes zoom level, and jitters instead of settling on the direction of travel.

## Product and platform

- Product: Uber Eats driver workflow
- Component: Built-in delivery map and orientation control
- Platform: iOS

## Environment

| Field | Value |
|---|---|
| Device | iPhone 14 Pro Max |
| OS version/build | Not recorded |
| Uber Eats version | Not recorded |
| Map mode | Built-in Uber Eats map |
| Device mounting and physical orientation | Not recorded |
| Network conditions | Not recorded |
| Date observed/documented | May 1, 2026 |

## Preconditions

- An Uber Eats delivery is active.
- The built-in Uber Eats map is visible.
- Location access and live position display are active.
- The map orientation control is available in the lower-right area of the map.

## Steps to reproduce

The issue is intermittent, so these steps describe the recurring field workflow rather than a guaranteed reproduction:

1. Start an Uber Eats delivery and open the built-in map.
2. Travel while observing the map's representation of the direction of movement.
3. When the map appears inverted or misaligned with the actual direction of travel, select the orientation control.
4. Observe the map camera's rotation and zoom behavior.
5. If the unstable behavior begins, touch and hold or manually reposition the map, then release it.
6. Restart Uber Eats, return to the map, and select the orientation control again.

## Actual result

- The map may initially show the direction of travel inverted or otherwise misaligned.
- After the orientation control is selected, the camera repeatedly:
  - rotates away from and back toward the travel direction;
  - changes zoom level in and out;
  - jitters instead of settling into a stable orientation.
- The combined movement makes map information difficult or impossible to interpret.
- Touching or holding the map may stabilize the view only temporarily; the movement resumes after release and may resume while the touch is still held.
- Restarting the application provides no reliable recovery: selecting the orientation control again can restart the unstable behavior.

## Expected result

Selecting the orientation control should smoothly align the map with the current travel direction and leave the camera stable. The control should not initiate repeated rotation, zoom changes, or jitter.

## Reproducibility

Intermittent and recurring during real delivery use. The behavior was described as frequent and long-standing, but no controlled attempt count, measured rate, first-observed date, or affected-version range was recorded. Informal percentage estimates from the field account are intentionally excluded.

## Severity

**High candidate.** The defect can make active navigation unreadable and increase distraction during driving. No collision, injury, or other physical incident is asserted.

## Priority

**To be assessed.** The user impact is substantial when the failure occurs, but the affected population, exact frequency, device/OS range, and availability of alternative navigation are unknown.

## Category

Functional / Navigation / Map Camera / Orientation / State Management / Visual Stability

## Workarounds observed

- Touching or holding the map may temporarily constrain the camera, but is not a reliable recovery.
- Restarting Uber Eats may clear the immediate state, but the problem can return after the orientation control is selected again.
- Switching to an external navigation provider is a possible avoidance path, but it was not evaluated as a controlled workaround in this observation.

## Evidence

- Firsthand verbal field account: available.
- Screen recording: not available in the shared source.
- Application, compass, location, motion-sensor, and map-camera logs: not available.
- No customer address, route, order, or location evidence is included in this report.

## Notes and limitations

- The report captures two linked visible states: an incorrect initial heading and camera instability triggered while attempting to correct it. The available account does not establish whether they share one technical cause.
- A conflict among compass, GPS heading, motion sensors, map auto-rotation, or camera-state logic is plausible but unproven.
- It is unknown whether the behavior depends on vehicle speed, device mount angle, portrait/landscape changes, magnetic interference, poor GPS accuracy, or a particular map zoom level.
- Apple Maps and Google Maps were not compared under the same controlled conditions.
- A future verification should record the exact OS and application builds, screen orientation, device mounting, compass calibration state, location accuracy, speed, zoom level, and a privacy-safe screen recording from before the control is selected through the unstable camera state.
