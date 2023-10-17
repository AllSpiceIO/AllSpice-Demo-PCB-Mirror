---

name: "AllSpice Pull Request Template"
about: "Optional description"

---

*This short description prepends any pull request. It is fully markdown compatible. See [markdown guide](https://www.markdownguide.org/cheat-sheet/) for examples of what you can do!*

## Resolved Issues
<!-- Include any relevant issues closed by this pull request. Use the form "Closes #<number of issue>" -->
...

## Description
<!-- Include a description for this design review. What is the primary purpose? What will be the status of this design after approval? -->
...

## Design Review Checklist
### Process
- [ ] Schematic and PCB file names follow standard
- [ ] Export necessary review files (3D model, BOM, etc.)
- [ ] Update relevant system architecture documents
- [ ] Update project README page
- [ ] Simulations uploaded and outputs explained
### System
- [ ] Power
  - [ ] Sufficient power supplied from upstream source
  - [ ] Supply rated for necessary country specifications
  - [ ] Estimated total worst-case power supply draw
- [ ] Connectors
  - [ ] I/Os are specified
  - [ ] Sufficient Current and Voltage rating
  - [ ] Mating connectors have matching pinout
  - [ ] Same contact material specified for mating connectors
- [ ] Testing
  - [ ] Test procedure written
- [ ] Environmental
  - [ ] Specified min/max operating temperature
  - [ ] Specified min/max storage temperature
  - [ ] Specified min/max humidity
- [ ] ROHS compliance requirement review
### Components
- [ ] Unpopulated components are denoted DNI
- [ ] Components meet environmental specifications
- [ ] All components have quantity, reference designator and description
- [ ] Suggested and alternate manufacturers listed
- [ ] Price and stock checked for each component
- [ ] Component derating
  - [ ] Voltage
  - [ ] Current
  - [ ] Power at worst-case operating temperature
  - [ ] Temperature at worst-case power
### Schematics
- [ ] Document
  - [ ] Dot on each connection
  - [ ] No four-point connections
  - [ ] Title block completed for each sheet
  - [ ] All components have reference designators and values
  - [ ] Multi-part components don't have unplaced symbols
  - [ ] Page title present and consistent on all pages if not in title block
  - [ ] Symbols identify open collector/drain pins and internal pulled up/down pins
  - [ ] Pin names and attributes on symbols with multi-function pins should match actual design usage (I/O/Bi, Name)
  - [ ] Components follow preferred reference designator pattern <!-- Link to spec -->
- [ ] External I/O
  - [ ] Filtered for EMI
  - [ ] Protected against electrostatic discharge (ESD)
  - [ ] Unused inputs terminated
- [ ] Microcontrollers / ICs
  - [ ] Predictable or controlled power-up state
    - [ ] Reset filtered
  - [ ] Sufficient bypass capacitance
  - [ ] Oscillators checked for reliable startup
  - [ ] Pullups on open-collector pins
  - [ ] Logic-low and logic-high voltage levels checked
  - [ ] No-connect pins labeled NC
  - [ ] Clock lines with series termination and parallel termination component locations present even if not populated; zero ohm resistor for series, unpopulated parts for parallel termination
  - [ ] Check for input voltages applied with power off and CMOS latchup possibilities
  - [ ] Check the data sheet errata and apnotes for weird IC behaviors
- [ ] Busses
  - [ ] UART/USART TX->RX and RX<-TX
  - [ ] I2C SDA and SCL pullup with appropriate value [per capacitance](https://www.ti.com/lit/an/slva689/slva689.pdf)
  - [ ] Setup, hold, access times for data and address busses
- [ ] Analog
  - [ ] Sufficient power rails for analog circuits
  - [ ] Amplifiers checked for stability
  - [ ] Consider signal rate-of-rise and fall for noise radiation
- [ ] General
  - [ ] Sufficient bulk capacitance calculated
  - [ ] Polarized components checked
  - [ ] Electrolytic/tantalum capacitors checked for no reverse voltage
  - [ ] Electrolytic/tantalum capacitors temperature/voltage derating sufficient for MTBF
  - [ ] Sufficient capacitance on low dropout voltage regulators
  - [ ] Sufficient time delays and slew rates for comparators
  - [ ] Sufficient common mode input voltage rating on opamps
  - [ ] Check pin numbers of all custom-generated parts
  - [ ] Check reverse base-emitter current/voltage on bipolar transistors
  - [ ] Power nets use preferred and consistent naming (ex. no `3.3V` vs `+3.3V`)
  - [ ] Debug resources added by design (leds, serial ports, etc.) even if unpopulated by default
### PCB
- [ ] Manufacturing
  - [ ] PCB manufacturing requirements noted on `fab` layer
    - [ ] Plating specified
      - [ ] Plating material
      - [ ] Plating thickness
    - [ ] Layer stack-up specified
    - [ ] Minimum trace/space specified
    - [ ] Minimum hole size specified
    - [ ] PCB color specified
    - [ ] Silkscreen color specified
    - [ ] Controlled impedance specified
    - [ ] Blind or buried vias specified
    - [ ] Panelization specified
      - [ ] External routing specified (ex. v-groove vs route)
    - [ ] Drill table generated
    - [ ] All specifications exceed manufacturing tolerance
  - [ ] Space between power planes minimized
  - [ ] Solder paste openings proper size
  - [ ] Fiducials placed if necessary
- [ ] Footprints
  - [ ] Pin 1 marked in a consistent manner
  - [ ] Component polarity marked
    - [ ] Diodes, LEDs
    - [ ] Electrolytic, tantalum capacitors
    - [ ] Keyed components like connectors
  - [ ] Footprint dimensions cross-checked with datasheet recommendation
  - [ ] Sufficient thermal pads on high-power components or nets
- [ ] Placement
  - [ ] Jumpers accessible
  - [ ] Debug connectors accessible
  - [ ] Filter resistors closer to source
  - [ ] Termination resistors close to target
  - [ ] Small loop path on switch-mode power supplies
  - [ ] Bypass capacitors close to ICs
  - [ ] Bypass capacitors close to connectors
  - [ ] Drivers / receivers close to connectors
  - [ ] SMT components on top side, through-hole components on bottom side if possible
- [ ] Clearance
  - [ ] Keep-out areas honored
    - [ ] Around mounting holes
    - [ ] For programming tools
    - [ ] For assembly tools (wrenches, screwdrivers etc.)
    - [ ] For connectors
  - [ ] Trace-to-trace clearance based upon voltage rating
  - [ ] Component size based upon voltage rating
  - [ ] Keep components away from board edge
- [ ] Mechanical
  - [ ] CAD file uploaded
  - [ ] Clearance above connectors
  - [ ] Clearance below through-hole components
  - [ ] Enough space for the minimum bending radius of the wire harness
  - [ ] Mounting holes electrically isolated if necessary
    - [ ] Mounting holes have via stitching
  - [ ] Hole diameters leave margin for plating
  - [ ] Board outline defined
  - [ ] Mechanical enclosure defined
  - [ ] Internal corners are rounded and can be milled
- [ ] Electrical
  - [ ] All traces are routed
  - [ ] Analog and digital commons joined at only one point
  - [ ] ERC passes
  - [ ] Isolation barriers are large enough
- [ ] Signal integrity
  - [ ] Gaps in ground planes checked and minimized
  - [ ] High-speed signals avoid gaps in ground planes
  - [ ] Stubs minimized for high-speed signals
  - [ ] Differential pair spacing based upon impedance matching
  - [ ] Transmission lines terminated with an appropriate impedance
  - [ ] Crystal connections kept short
  - [ ] Guard ring around crystals
  - [ ] Traces avoided under sensitive components
  - [ ] Traces avoided under noisy components
  - [ ] Via fencing of sensitive RF transission lines done with the proper via spacing (< 1/20 lambda)
  - [ ] Option for a shielding can over sensitive circuitry e.g. RF?
- [ ] Copper pour
  - [ ] All planes have been poured
  - [ ] Planes and pours checked for high-impedance paths
  - [ ] No pour between adjacent pins on ICs
- [ ] Traces
  - [ ] Trace-pad connections sufficiently obtuse (angle 90 deg or more)
  - [ ] Trace widths sufficient for the current draw and max heating
  - [ ] No connections between adjacent pins on ICs
  - [ ] Vias for internal power traces sufficiently large
  - [ ] Mitered bends or soft curves (r > 3 trace width) for impedance sensitive traces
- [ ] Thermal
  - [ ] Temperature sensitive components placed away from hot components
  - [ ] Thermal vias in thermal pads
- [ ] Testing
  - [ ] Test points on PCBs for critical circuits, hard to reach nets
  - [ ] Ground connection points close to analog test points
- [ ] Silk screen
  - [ ] Notes and documentation
    - [ ] Updated revision number
    - [ ] Updated date
    - [ ] Blank space designated for a serial / assembly number
  - [ ] No silk screen over pads / vias
  - [ ] Text is readable from at most two directions
  - [ ] Silk screen size / font will legible after printing
  - [ ] Connector pin-outs labeled
  - [ ] Fuse size and type marked on PCB
  - [ ] Functional groups marked
  - [ ] Functionality labeled
    - [ ] Test points
    - [ ] LEDs
    - [ ] Buttons
    - [ ] Connectors/terminals
    - [ ] Jumpers/fuses

<!-- Special thanks to Henrik Enggaard Hansen for https://pcbchecklist.com/ -->