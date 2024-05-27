# Sensible Configuration

The file `./printer.cfg.orig` is the `printer.cfg` that originally
shipped with the X-Smart 3. It's added here for reference purposes.

## Configuration

To help clean up and organize the configuration, the original
`printer.cfg` has been split up an organized into it's own directory.

The file tree looks like this:

```
.
├── printer.cfg
├── printer.cfg.orig
├── README.md
└── x-smart-3
    ├── 00-hardware.cfg
    ├── 01-steppers.cfg
    ├── fans.cfg
    ├── macros.cfg
    ├── pins.cfg
    └── temps.cfg
```

## Changes

These config files contain changes for the mods in this repository.
Changes include:

- Mainboard fan mod
- Fan renaming
- Set fans to 100% on MCU error
- Activate temperature sensor on the Pi
- Macro updates

## Notes

Because the fans names are hardwired into the display screen firmware,
using these configs will make the `fan1` and `fan3` screen buttons
inoperative.
