# NAME

bcalc - Bitrate-speed-size calculator

# SYNOPSIS

bcalc \[options\] SIZE SIZE\_UNIT @ SPEED SPEED\_UNIT

or

bcalc \[options\] DURATION DURATION\_UNIT @ SPEED SPEED\_UNIT

# DESCRIPTION

Calculate the time it takes to transfer files of a given size at a given speed.
Or calculates the resulting size for a given duration and bitrate.

The spaces between arguments are optional.

# SIZE UNITS

In size units, an uppercase B means Bytes (8 bits). A lowercase b means bits.
The size can be prefixed with a one-letter or full unit name. The following
are valid size units:

    b or bits
    B or Bytes
    kb or kilobits
    kB or kilobytes
    etc. with Mb, MB, Gb, GB, Tb, TB

The greatest recognized size unit is TeraBytes. That should be enough for a couple
of years...

# SPEED UNITS

Speed units are the same as size units, suffixed with "ps" (per second). For example:

    bps, Mbps, MBps Megabytesps, ...

# DURATION UNITS

Valid duration units are:

    s or sec or seconds
    m or mn or minutes
    h or hours

# OPTIONS

- **-?** or **-h**

    Print a brief help message and exit.

- **--help**

    Print the manual page and exit.

- **-v** or **--verbose**

    Print details of conversions done

- **-d** or **--debug**

    Print even more details of argument analysis and conversions

# EXAMPLES

The following all print out the same result:

    bcalc 7 GB @ 90 KBps
    bcalc 7GB@90KBps
    bcalc 7 Giga bytes @ 90Kilobytesps
    bcalc 7 Giga bytes @ 90Kilobytespersecond
    bcalc 7 Giga bytes @ 90 Kilobytes per second
    bcalc 7 G bytes @ 90 Kilobytes per second

    = 21.60 hours

Or calculate size from duration:

    bcalc 1mn @ 120Mbps

    bcalc 1h  @ 120Mbps

# CHANGES
  0.32 : clearer warning if speed\_unit not found
  0.3 : accept "pm" for "per minute" as in 6GBpm

# AUTHOR

mi dot deb at alma dot ch, 2010-2013,2018
