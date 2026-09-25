# Electrical & Sensor Interfacing Schematics

This directory stores electrical circuit schematics, wiring harnesses, PCB layout files (KiCad), and power distribution diagrams for the smart mulberry cutting machine.

## Subdirectory Structure
- `circuits/`: KiCad project files (`.kicad_sch`, `.kicad_pcb`).
- `wiring/`: System-level electrical interconnection and harness drawings (`.pdf`, `.svg`).
- `pinouts/`: Pin mapping documentation between microcontroller, motor drivers, and sensor breakout boards.

## Engineering Standards
- All schematics must adhere to IEC 60617 graphical symbols.
- Galvanic isolation must be maintained between the 48V power stage and the 3.3V/5V logic bus via optocouplers or digital isolators.
- Emergency stop lines must break primary power via hardware contactors independently of microcontroller software.
