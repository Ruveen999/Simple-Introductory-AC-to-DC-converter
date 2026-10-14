# Simple Introductory AC to DC Converter

An introductory LTspice project exploring AC-to-DC conversion using a full-wave bridge rectifier, a smoothing capacitor, and an adjustable linear regulator.

## Project Objectives

- Understand how a bridge rectifier uses both halves of an AC waveform.
- Observe the difference between pulsating DC and filtered DC.
- Investigate capacitor charging, discharging, and output ripple.
- Use an adjustable regulator to obtain a steady DC output.

## Circuit Stages

### 1. Full-Wave Bridge Rectifier

Four diodes convert the AC input into a unidirectional voltage across the load.

- D1 and D2 conduct during the positive half-cycle.
- D4 and D3 conduct during the negative half-cycle.
- Current flows through the load in the same direction during both half-cycles.

The output is pulsating DC and falls close to zero between peaks.

### 2. Capacitor Filtering

A capacitor is connected in parallel with the load.

It charges near the rectified voltage peaks and supplies current to the load between peaks, reducing the variation in output voltage.

The initial capacitor experiment showed little visible smoothing. This illustrates that adding a capacitor alone does not guarantee low ripple: its capacitance and the load current affect how quickly it discharges.

### 3. Voltage Regulation

The final circuit uses an LT317A adjustable linear regulator after the smoothing capacitor.

A resistor network connected to the adjustment terminal sets the output voltage. The regulator maintains a nearly steady output while its input provides sufficient voltage and the load remains within its operating limits.

## Components

| Component | Purpose |
|---|---|
| Sinusoidal voltage source | Provides the AC input |
| Four diodes | Form the full-wave bridge rectifier |
| Smoothing capacitor | Stores energy and reduces ripple |
| LT317A regulator | Regulates the DC output |
| Adjustment resistors | Set the regulator output voltage |
| Load resistor | Represents the connected load |

The component values used for each experiment are shown in the circuit schematics.

## Simulation Results

The screenshots document the progression through the project:

1. Bridge rectifier schematic.
2. AC input compared with the full-wave rectified output.
3. Initial capacitor-filter experiment with little visible smoothing.
4. Final circuit with capacitor filtering and voltage regulation.
5. Final waveform comparing the regulator input and output.

In the final simulation, the regulator input shows repeated capacitor charging and discharging. The output appears steady at the displayed graph scale.

## How to Run

1. Download the repository files.
2. Open the final `.asc` circuit file in LTspice.
3. Run the transient simulation.
4. Probe the regulator input and output wires to compare their voltages.
5. Zoom into the waveforms to inspect ripple and startup behavior.

For the bridge-only circuit, measure the voltage across the load using a differential voltage probe.

## Lessons Learned

- A diode's bias changes when the AC source reverses polarity.
- Current trace polarity depends on the simulator's reference direction.
- All LTspice ground symbols represent the same electrical node.
- Bridge rectification produces pulsating DC.
- Capacitor filtering reduces ripple but does not eliminate it.
- A regulator can maintain a steady output despite input ripple when sufficient voltage headroom is available.

## Limitations

This is an introductory simulation project, not a hardware-validated power supply.

Further work is needed to assess:

- Regulator current limits and heat dissipation.
- Diode current ratings and losses.
- Capacitor voltage rating, ripple current, and charging surge.
- Output behavior under different loads.
- Required supporting components from the regulator datasheet.

A flat simulated output does not by itself confirm that the circuit is suitable for physical construction.

## Tools Used

- LTspice — circuit design and transient simulation
