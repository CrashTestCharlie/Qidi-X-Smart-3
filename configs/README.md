# Sensible Configuration

The file `./printer.cfg.orig` is the `printer.cfg` that originally
shipped with the X-Smart 3. It’s added here for reference purposes.

## Configuration

To help clean up and organize the configuration, the original
`printer.cfg` has been split up an organized into it’s own directory.

The file tree looks like this:

    .
    ├── printer.cfg
    ├── printer.cfg.orig
    ├── README.md
    └── x-smart-3
        ├── 00-hardware.cfg
        ├── 01-steppers.cfg
        ├── control.cfg
        ├── fans.cfg
        ├── macros.cfg
        ├── pins.cfg
        └── temps.cfg

The `PRINT_START` type macros are found in `control.cfg` which contains
the macros that will most likely need personalization.

## Changes

These config files contain changes for the mods in this repository.
Changes include:

- Mainboard fan mod
- Fan renaming
- Set fans to 100% on MCU error
- Activate temperature sensor on the Pi
- Macro updates

## Config Installation

### From a remote computer

First clone this repository to your computer and make sure you can
access the X-Smart 3 via `ssh`.

#### Backup

Before using these configs, you should backup your original
`printer.cfg`. This only needs to be done once and your original file
will be in the X-Smart 3’s home directory named `printer.cfg.orig`:

    ssh mks@mkspi.local "mv klipper_config/printer.cfg printer.cfg.orig"

#### Installation

To easily install the configs, use `rsync`. From inside the `configs`
directory, run:

    rsync -aRv printer.cfg x-smart-3/ mks@mkspi.local:klipper_config

### From the X-Smart 3

If you have cloned this repository to the X-Smart 3, use these commands
to install the new configs.

#### Backup

Before using these configs, you should backup your original
`printer.cfg`. This only needs to be once and your original file will be
found in the home directory named `printer.cfg.orig`:

    mv klipper_config/printer.cfg ./printer.cfg.orig

#### Installation

From within the `configs/` directory of this repository, copy the
configs to the correct location:

    cp -rt /tmp/klipper_config/ printer.cfg x-smart-3/

#### Finishing up

Now, from the web interface, verify that the new configs are in place,
and restart Klipper to see the changes.

## Notes

Because the fans names are hardwired into the display screen firmware,
using these configs will make the `fan1` and `fan3` screen buttons
inoperative.
