# [Sucker Subsystem](../../src/main/java/org/robolancers321/subsystems/intake/Sucker.java)

## Description
This subsystem controls the rollers on the intake of the 321 robot and can interface with the motor controlling the roller and the touch sensor on the roller that detects if a note is inside the intake. 

## Connected Devices
- Sucker motor (`CANSparkMax` Motor) for powering the rollers
- Touch sensor (`DigitalInput`) for detecting if a note is in the intake

## Methods

| Method Name | Returns | Parameters | Description | Notes |
| --- | --- | ---- | ---- | --- |
| `getVelocityRPM` | `double` | N/A | Getter for the speed of the intake motor in rotations per minute (RPM) |
| `noteDetected` | `boolean`  | N/A | Uses the touch sensor in the intake to sense whether or not we have a note
| `off` | `Command`  | N/A | Creates a command to stop the intake | This command will run **forever** if not interrupted |
| `offInstantly` | `Command` | N/A | Same as `off` but command runs once instead of forever | This command will run **once** and stop |
| `in` | `Command` | N/A | Creates a command that intakes a note by running rollers inwards |  |
| `ampShot` | `Command` | N/A | Creates a command that outtakes a note to amp by running the rollers outwards at a certain rpm |  |
| `out` | `Command`  | N/A | Creates a command that ejects a note by running rollers outwards |  |

## Periodic
### Logging
This subsystem logs the following values onto the dashboard:
| Name | Value | Notes |
| ---- | ----- | ----- |
| `sucker rpm` | How fast the sucker is moving in RPM | Uses the `getVelocityRPM()` method|
| `sucker detects note` | Whether or not the intake detects a note | Uses the `noteDetected()` method |
| `sucker output` | How much power we are supplying to the sucker motor from `-1 to 1` | |


