This is a fork of https://github.com/andrivet/ADVi3pp-Marlin

There are few settings in original firmware that don't make me so happy in the legacy firmware:

* the bed leveling is slow ... SO SLOW
* why use the legacy switch, while we have a BLTOUCH to do the job ?

Here are 2 new variants of the firmware. Both of them are compatible with the screen (BLTOUCH mode).

## i3plus-bltouch-zmax

This is the renamed legacy "i3plus-bltouch", but the 2nd probe speed is set 4x faster.

```c++
#define Z_PROBE_SPEED_SLOW (Z_PROBE_SPEED_FAST / 2)
```

## i3plus-bltouch-zmin

This variant remap and invert the Z_MAX and Z_MIN pin. The behavior is completely different:

* the Z stop switch is not used anymore
* the BLTOUCH is used for Z homing + probing
* Z homing is made at the middle of the bed (X & Y)

## how to build your own firmware

* checkout the "advipp-3.0.2-patch" branch of this repository
* open and build with platformio